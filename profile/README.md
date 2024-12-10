# Kalnaslab-org
GitHub Organization for the LASP Kalnajs Team.

[All Repositories](https://github.com/kalnajslab-org/repositories)

## Teensy Firmware Quickstart

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
1. For PlatformIO:
    1. Create a *.cpp* link in */src* to the *.ino* file. (E.g. *src/StratoCore_LPC.cpp -> ../StratoCore_LPC.ino*)
1. To switch back to ArduinioIDE from PlatformIO:
    1. Remove *src/main.cpp*
    2. Remove *.pio/* 

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

The main program for our application is the *.ino* file at the top level of the
repository. PlatformIO doesn't expect here to be a source file here, and so it will
not compile it, leading to link errors. So we create a link which makes it visible 
to the dependency scanner (e.g.):

```sh
cd src
ln -s ../StratoCore_RATS.ino StratoCore_RATS.cpp
```
If you get an `undefined reference to 'loop'` error during the build,
then you have not added the *.cpp* link to the *.ino* file.

Library requirements are specified in *platformio.ini*, and they are
fetched automagically, so that *libraries/* is ignored by PlatformIO.

PlatformIO creates the *.pio/* tree to hold all of the build artifacts.
As mentioned above, this tree and *src/main.cpp*, give ArduinoIDE great 
indigestion. and they are removed as necessary. 


