# Kalnaslab-org
GitHub Organization for the LASP Kalnajs Team.

[All Repositories](https://github.com/orgs/kalnajslab-org/repositories)

## Teensy Firmware Quickstart

_We have decided it will be simpler just to use separate Git repository clones for each of the
development environments. You can use either one._

1. If using the ArduinoIDE build environment:
    1. Create *Sketchbook/* and *Sketchbook/libraries/* directories.
       (You may already have this as *~/Documents/Arduino/* or some other Sketchbook directory).
    1. Clone the main applications (e.g. *StratoCore_LPC.git*) into *Sketchbook/libraries/*.
    1. For ArduinoIDE:
        1. Clone LASP support libraries (e.g. *StrateolXML.git*) into *Sketchbook/libraries/*.
        1. Unzip ZIP libraries (e.g. *StratoCore_LPC/zips/\*.zip*) into *Sketchbook/libraries/*.
        1. From ArduinoIDE:
            1. In *Settings*, set Sketchbook location to *Sketchbook/*.
            1. Use library manager to install standard libraries (e.g. *TinyGPSPlus*).
        1. Open the *.ino* file (e.g. *StratoCore_LPC.ino*) in ArduinoIDE.
1. If using the PlatformIO build environment:
   1. Clone the main application (e.g. *StratoCore_LPC.git*) into whatever directory you are using
      for StratoCore PlatformIO development.
   1. Create a *.cpp* link in */src* to the *.ino* file. (E.g. *src/StratoCore_LPC.cpp -> ../StratoCore_LPC.ino*)

More [ArduinoIDE details](#arduinoide) and [PlatformIO details](#platformio) are found below.

## Repositories Summary

### Laser Particle Counter (LPC)
Main Board:
1. StratoCore_LPC
2. StratoCore
3. StrateoXML
4. StratoLinduino
5. RS41

Particle Counter:
1. PHA_V5_1

### RATS
Main Board:
1. StratoCore_RATS
2. StratoCore
3. StrateoXML
4. ECUcomm

Reel Controller:
1. MCB_T4.1

End Control Unit (ECU):
1. ECU
2. ECUcomm

### RATCHUTS
Main Board Teensy:
1. StratoPIB
2. StratoCore
3. StrateoXML

Reel Controller Teensy:
1. MCB_T4.1

## Firmware Development Environments

We support two firmware development environments:
- ArduinoIDE: The tried-and-true hobbiest-oriented tool. It is the mainstay in the Arduino community,
  but is maddenly frustrating for projects with any level of complexity.
- PlatformIO: A more modern framework which combines VSCode and Scons to provide a more productive
  environment, including rigourous configuration definitions, Intellisense, Git integration,
  and more.

With a few workarounds, the kalnajslab-org repositories can be used in either environment. A
workflow is documented here which describes how to do this.

### Prerequisites

1. We use a directory structure that will accomodate both techniques.
   Create a top level directory, which will be the *Sketchbook* location.
   (You may already have one, typically *~/Documents/Arduino/*.) Add a *libraries/* sub-directory:
```sh
Sketchbook/ 
          |
          --libraries/
```
1. Run the ArduinoIDE. Open the *Settings*, and set the Sketchbook path to your
   *Sketchbook* directory.
1. Libraries for ArduinoIDE will be located in the *Sketchbook/libraries/*;
   they are searched by that tool. These will be populated from any of:
   - The ArduinoIDE library manager.
   - `git clone` of one of our repositories.
   - Unzipping of a library zip file.
1. Clone the applications (e.g.*StratoCore_RATS*) into *Sketchbook/libraries/*.

### ArduinoIDE

There are a couple of PlatformIO items which cause the ArduinoIDE to
go bonkers. So:
1. Remove the *src/.cpp* link that you may have made for working with PlatformIO.
2. Remove the *.pio* directory.

Now you should be able to run the ArduinoIDE, open the *.ino* file, and build/upload/monitor the
application.

If you get an `The sketch file 'TinyGPS++.cpp' cannot be used.` error when
opening the sketch, then you have not removed *.pio/*. If you get missing
header files, then you have not removed the *.cpp* link.

Note that in some cases, ArduinoIDE works fine for main application located in
*Sketchbook/*. But there is at least one case (*MCB_T4.1*), where this doesn't
work because the *Technosoft* library references a header file in *MCB_T4.1*.
So just stick main apps and libraries in *Sketchbook/libraries/*.

### PlatformIO

#### PlatformIO IDE
- Open VSCode
- Install the PlatformIO extension.
- Extra credit: Install the excellent Serial Monitor extension from Microsoft.

That should be it. An "alien" button will appear on the left toolbar, and
"house" and "camera" buttons will appear on the bottom status bar.

- Alien button: Will bring up Project Task choices, where you can clean, build, upload, etc.
- House button: This opens PlatformIO automation. I haven't found it very useful.
- Camera button: This opens a dropdown selector at the top of the window, where you can
  choose the built target of choice. We generally don't have more than one target.
  But, for MCB_T4.1 (for example), there are targets for either a RACHUTS or RATS MCB
  build.
  
#### StratoCore Instrument Project Setup

The main program for our application is the *.ino* file at the top level of the
repository. _setup()_ and _loop()_ live here, and because
PlatformIO doesn't expect a source file to be here, it will
not compile it, leading to linker errors. So we create a symbolic link which makes 
it visible to the dependency scanner (e.g.):

```sh
cd src; ln -s ../StratoCore_RATS.ino StratoCore_RATS.cpp
```
If you get an `undefined reference to 'setup'` error during the build,
then you have not added the *.cpp* link to the *.ino* file.

Library requirements are specified in *platformio.ini*, and they are
fetched automagically.

PlatformIO creates the *.pio/* tree to hold all of the build artifacts.
All library references are downloaded from the PlatformIO repo or 
GitHub, into *.pio/libdeps/<env>/*.

As mentioned above, the *.pio/* tree and *src/main.cpp*, give ArduinoIDE great 
indigestion, and they are removed if you want to use the same git repo clone with
both environments. 

#### Editing Library Dependencies (IMPORTANT)

The StratoCore application _platformio.ini_ lists libraries which are downloaded
from GitHub (or other places). During most development we will only be editing the
application source code that has been cloned into _src/_. But sometimes
we may want to make changes to a library. It's a bit convoluted to do this.
The issue is how to commit your edits.

The process is to open the source code that has been cloned by PlatformIO
into _.pio/libdeps/<env_name>/<library_name>_. The easiest way to find
the code is to right-click on the function call in the app code, 
navigate to the definition, and edit/build/test.

Edits will appear in the VSCode Source Control pane, and you can
commit them from here. _BUT if you do a PlatformIO "Clean All",
before commiting and pushing, you will loose all of your edits._
This is because "Clean All" erases everything in _.pio/_. (A
simple "Clean" is OK).

#### Environments and platformio.ini

PlatformIO has the concept of _environments_, which are much like
build targets. They are defined by _[env:name]_ sections in 
_platformio.ini_. We use them to customize builds for specific purposes,
e.g customizing the MCB firmware between RATS, RACHUTS and FLOATS,
or building firmware that shares the log and Zephyr ports.

It is not very obvious, but there is an environment chooser button at
the _bottom_ of the VSCode window, which opens a chooser at the _top_ of the
VSCode window! If you have (say) 2 environments defined, it will offer you both of them, as well
as _Default_. Selecting an environment causes it to appear in the Alien panel. 
Selecting _Default_ causes all of them to appear in the Alien panel, as well
as a top one where you can build all targets at once.

#### Upload and Monitor Ports

It turns out that _upload_port_ parameter doesn't seem to work with the uploader that Teensy 
provides. This means that the following _platformio.ini_ parameter does nothing:
```
  upload_port=/dev/cu.usbmodem165659901
```
See this [issue](https://github.com/platformio/platform-teensy/issues/44).

But there is a very handy port selector, once again at the _bottom_ of VSCode_, which
(once again) opens a selector at the _top_ of VSCode. It is initially set to _Auto_;
just change it to the correct port and uploads/monitors will work, and you can leave
multiple Teensies plugged in.

Just make sure that you have the correct one chosen, otherwise you may flash the MCB
with the StratoCore_LPC code and vice versa!
