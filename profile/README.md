# Kalnaslab-org
GitHub Organization for the LASP Kalnajs Team.

[All Repositories](https://github.com/orgs/kalnajslab-org/repositories)

## Repositories

### Instrument Applications

| Repository | Description |
|---|---|
| [StratoCore_LPC](https://github.com/kalnajslab-org/StratoCore_LPC) | Main board application for the Laser Particle Counter |
| [StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS) | Main board application for the Reel-down Aerosol and Temperature Sampler |
| [StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) | Main board application for the RAdiative and CHemical composition Using Tethered Sondes |
| [PHA_V5_1](https://github.com/kalnajslab-org/PHA_V5_1) | Pulse Height Analyzer firmware for the LPC particle counter board |
| [ECU](https://github.com/kalnajslab-org/ECU) | End Control Unit firmware for the RATS tether reel system |
| [RPU](https://github.com/kalnajslab-org/RPU) | RACHuTS profiling unit |
| [MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1) | Motor Control Board firmware for RATS/RACHUTS, updated for Teensy 4.1 |
| [RS41](https://github.com/kalnajslab-org/RS41) | Support library for the Vaisala RS41 radiosonde |

### Core Firmware Libraries

| Repository | Description |
|---|---|
| [StratoCore](https://github.com/kalnajslab-org/StratoCore) | Core framework for all LASP Stratéole 2 instrument main boards |
| [StrateoleXML](https://github.com/kalnajslab-org/StrateoleXML) | XML-based communications library for interfacing with the CNES Zephyr OBC |
| [ECUcomm](https://github.com/kalnajslab-org/ECUcomm) | LoRa-based communications protocol between the RATS ECU and main board |
| [MCBComm](https://github.com/kalnajslab-org/MCBComm) | Communications protocol library for the Motor Control Board |
| [RPUComm](https://github.com/kalnajslab-org/RPUComm) | Communications protocol library for the RATCHuTS Profiling Unit |
| [SerialComm](https://github.com/kalnajslab-org/SerialComm) | Simple, robust protocol and class for inter-Arduino UART communication |
| [SafeBuffer](https://github.com/kalnajslab-org/SafeBuffer) | Bounds-checked buffer library for embedded C++ |
| [TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM) | Robust library for storing and retrieving configurations in Teensy EEPROM |
| [Tsensor1Wire](https://github.com/kalnajslab-org/Tsensor1Wire) | Library for one-wire temperature sensors |
| [StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino) | Hardware support files cherry-picked from the ADI Linduino repository |
| [Technosoft](https://github.com/kalnajslab-org/Technosoft) | Interface library for Technosoft motor controllers |

### Ground Support Software

| Repository | Description |
|---|---|
| [ZephyrSim](https://github.com/kalnajslab-org/ZephyrSim) | Upgraded OBC_Simulator (Qt6) tool for simulating CNES Zephyr OBC communications |
| [TMmonster](https://github.com/kalnajslab-org/TMmonster) | TM decoder tool, the Swiss Army Knife of TM decoding |
| [TeleCommands](https://github.com/kalnajslab-org/TeleCommands) | Python tool for generating telecommands for LPC, RACHUTS, and FLOATS instruments |

### Obsolete

| Repository | Description |
|---|---|
| [MCB](https://github.com/kalnajslab-org/MCB) | Motor Control Board firmware for the RACHUTS MonDo reel board |
| [PUCode](https://github.com/kalnajslab-org/PUCode) | 1st generation firmware for the RACHuTS profiling unit, and the communications protocol between the Profiling Unit and RACHUTS. Replaced by [RPU](https://github.com/kalnajslab-org/RPU) and [RPUComm](https://github.com/kalnajslab-org/RPUComm). |
| [OBC_Simulator](https://github.com/kalnajslab-org/OBC_Simulator) | On-board computer simulator for ground testing of Stratéole 2 instruments |
| [SerialComm-LarsObsolete](https://github.com/kalnajslab-org/SerialComm-LarsObsolete) | Obsolete version of SerialComm, retained for reference |
| [TMdecoder](https://github.com/kalnajslab-org/TMdecoder) | Decoder for LASP instrument telemetry streams |
| [StratoCore_FLOATS](https://github.com/kalnajslab-org/StratoCore_FLOATS) | Main board application for the FLOATS instrument |

### Cloud

| Repository                                                         | Description                                                                                                |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| [KalCloud](https://github.com/kalnajslab-org/KalCloud) _(private)_ | Cloud infrastructure for real-time system monitoring, messaging, data processing, and product distribution |
| [KalCloudGrafana](https://github.com/kalnajslab-org/KalCloudGrafana) _(private)_ | Repoistory for just the grafana dashboards. Keep separate for finer write access control |

### Hardware

| Repository                                                           | Description                              |
| -------------------------------------------------------------------- | ---------------------------------------- |
| [Hardware](https://github.com/kalnajslab-org/Hardware) _(private)_   | PCB schematics and hardware design files |

### ASPEN

| Repository | Description |
| --- | --- |
| [SbdMail](https://github.com/kalnajslab-org/SbdMail) | Downloads Iridium SBD emails and decodes LASP-specific attachments |
| [VHFtracker](https://github.com/kalnajslab-org/VHFtracker) | Firmware for the VHF beacon which uses APRS to transmit location data of an instrument |
| [TrackerFinder](https://github.com/kalnajslab-org/TrackerFinder) | Capture AX25 messages sent by a VHF tracker |
| [WindBug](https://github.com/kalnajslab-org/WindBug) | Scrapes the JSOC web page and sends email alerts when wind criteria are met |

### Skysonde Plugins

| Repository | Description |
|---|---|
| [LopcCncPlugin](https://github.com/kalnajslab-org/LopcCncPlugin) | Skysonde Client plugin for the LOPC/CNC instrument |
| [HiStac2Plugin](https://github.com/kalnajslab-org/HiStac2Plugin) | Plugin for the HiStac2 instrument interface |

## Teensy Firmware Quickstart

_We have decided it will be simpler just to use separate Git repository clones for each of the
development environments. Note that we have since migrated exclusively to PlatformIO; see
[Firmware Development Environments](#firmware-development-environments) below._

1. If using the ArduinoIDE build environment:
    1. Create *Sketchbook/* and *Sketchbook/libraries/* directories.
       (You may already have this as *~/Documents/Arduino/* or some other Sketchbook directory).
    1. Clone the main applications (e.g. *StratoCore_LPC.git*) into *Sketchbook/libraries/*.
    1. For ArduinoIDE:
        1. Clone LASP support libraries (e.g. *StrateoleXML.git*) into *Sketchbook/libraries/*.
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

## Repositories Dependencies

Each row's Subsystem links to that subsystem's own repository; the dependency columns list what it depends on, so the subsystem's own repository is not repeated there.

### LPC

| Subsystem | kalnajslab-org Dependencies | External Dependencies |
|---|---|---|
| [Main Board](https://github.com/kalnajslab-org/StratoCore_LPC) | [StratoCore](https://github.com/kalnajslab-org/StratoCore)<br>[StrateoleXML](https://github.com/kalnajslab-org/StrateoleXML)<br>[StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino)<br>[RS41](https://github.com/kalnajslab-org/RS41) | TinyGPSPlus<br>WDT_T4 |
| [Particle Counter](https://github.com/kalnajslab-org/PHA_V5_1) | [StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino) | TinyGPSPlus |

### RATS

| Subsystem | kalnajslab-org Dependencies | External Dependencies |
|---|---|---|
| [Main Board](https://github.com/kalnajslab-org/StratoCore_RATS) | [StratoCore](https://github.com/kalnajslab-org/StratoCore)<br>[StrateoleXML](https://github.com/kalnajslab-org/StrateoleXML)<br>[ECUcomm](https://github.com/kalnajslab-org/ECUcomm)<br>[MCBComm](https://github.com/kalnajslab-org/MCBComm)<br>[StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino)<br>[TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM)<br>[SerialComm](https://github.com/kalnajslab-org/SerialComm) | TinyGPSPlus<br>WDT_T4<br>LoRa<br>ArduinoJson<br>TeensyID<br>Embedded Template Library (ETL) |
| [Reel Controller](https://github.com/kalnajslab-org/MCB_T4.1) | [MCBComm](https://github.com/kalnajslab-org/MCBComm)<br>[TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM)<br>[SafeBuffer](https://github.com/kalnajslab-org/SafeBuffer)<br>[Technosoft](https://github.com/kalnajslab-org/Technosoft)<br>[Tsensor1Wire](https://github.com/kalnajslab-org/Tsensor1Wire)<br>[StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino)<br>[SerialComm](https://github.com/kalnajslab-org/SerialComm) | TinyGPSPlus<br>WDT_T4 |
| [End Control Unit (ECU)](https://github.com/kalnajslab-org/ECU) | [ECUcomm](https://github.com/kalnajslab-org/ECUcomm)<br>[RS41](https://github.com/kalnajslab-org/RS41) | TinyGPSPlus<br>WDT_T4<br>LoRa<br>DallasTemperature<br>ArduinoJson<br>TeensyID<br>Embedded Template Library (ETL) |

### RACHUTS

| Subsystem | kalnajslab-org Dependencies | External Dependencies |
|---|---|---|
| [Main Board](https://github.com/kalnajslab-org/StratoCore_RACHUTS) | [StratoCore](https://github.com/kalnajslab-org/StratoCore)<br>[StrateoleXML](https://github.com/kalnajslab-org/StrateoleXML)<br>[StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino)<br>[MCBComm](https://github.com/kalnajslab-org/MCBComm)<br>[TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM)<br>[SerialComm](https://github.com/kalnajslab-org/SerialComm)<br>[RPUComm](https://github.com/kalnajslab-org/RPUComm) | TinyGPSPlus<br>WDT_T4<br>LoRa |
| [Reel Controller](https://github.com/kalnajslab-org/MCB_T4.1) | [MCBComm](https://github.com/kalnajslab-org/MCBComm)<br>[TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM)<br>[SafeBuffer](https://github.com/kalnajslab-org/SafeBuffer)<br>[Technosoft](https://github.com/kalnajslab-org/Technosoft)<br>[Tsensor1Wire](https://github.com/kalnajslab-org/Tsensor1Wire)<br>[StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino)<br>[SerialComm](https://github.com/kalnajslab-org/SerialComm) | TinyGPSPlus<br>WDT_T4 |
| [Profiling Unit](https://github.com/kalnajslab-org/RPU) | [RPUComm](https://github.com/kalnajslab-org/RPUComm)<br>[SerialComm](https://github.com/kalnajslab-org/SerialComm)<br>[Tsensor1Wire](https://github.com/kalnajslab-org/Tsensor1Wire)<br>[RS41](https://github.com/kalnajslab-org/RS41) | TinyGPSPlus<br>WDT_T4<br>LoRa<br>Time<br>Embedded Template Library (ETL) |

## Reverse Dependencies

The inverse of the tables above: for each support library, the subsystems that need to be rebuilt if it changes.

| Library | Used By |
|---|---|
| [StratoLinduino](https://github.com/kalnajslab-org/StratoLinduino) | [StratoCore_LPC](https://github.com/kalnajslab-org/StratoCore_LPC)<br>[PHA_V5_1](https://github.com/kalnajslab-org/PHA_V5_1)<br>[StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) |
| [SerialComm](https://github.com/kalnajslab-org/SerialComm) | [StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS)<br>[RPU](https://github.com/kalnajslab-org/RPU) |
| [StratoCore](https://github.com/kalnajslab-org/StratoCore) | [StratoCore_LPC](https://github.com/kalnajslab-org/StratoCore_LPC)<br>[StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) |
| [StrateoleXML](https://github.com/kalnajslab-org/StrateoleXML) | [StratoCore_LPC](https://github.com/kalnajslab-org/StratoCore_LPC)<br>[StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) |
| [RS41](https://github.com/kalnajslab-org/RS41) | [StratoCore_LPC](https://github.com/kalnajslab-org/StratoCore_LPC)<br>[ECU](https://github.com/kalnajslab-org/ECU)<br>[RPU](https://github.com/kalnajslab-org/RPU) |
| [MCBComm](https://github.com/kalnajslab-org/MCBComm) | [StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) |
| [TeensyEEPROM](https://github.com/kalnajslab-org/TeensyEEPROM) | [StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1)<br>[StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS) |
| [ECUcomm](https://github.com/kalnajslab-org/ECUcomm) | [StratoCore_RATS](https://github.com/kalnajslab-org/StratoCore_RATS)<br>[ECU](https://github.com/kalnajslab-org/ECU) |
| [RPUComm](https://github.com/kalnajslab-org/RPUComm) | [StratoCore_RACHUTS](https://github.com/kalnajslab-org/StratoCore_RACHUTS)<br>[RPU](https://github.com/kalnajslab-org/RPU) |
| [Tsensor1Wire](https://github.com/kalnajslab-org/Tsensor1Wire) | [MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1)<br>[RPU](https://github.com/kalnajslab-org/RPU) |
| [SafeBuffer](https://github.com/kalnajslab-org/SafeBuffer) | [MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1) |
| [Technosoft](https://github.com/kalnajslab-org/Technosoft) | [MCB_T4.1](https://github.com/kalnajslab-org/MCB_T4.1) |

## Firmware Development Environments

We started out supporting two firmware development environments:
- ArduinoIDE: The tried-and-true hobbyist-oriented tool. It is the mainstay in the Arduino community,
  but is maddeningly frustrating for projects with any level of complexity.
- PlatformIO: A more modern framework which combines VSCode and SCons to provide a more productive
  environment, including rigorous configuration definitions, Intellisense, Git integration,
  and more.

With a few workarounds, the kalnajslab-org repositories could be used in either environment. A
workflow is documented here which describes how to do this.

Since then, we have gradually migrated exclusively to the PlatformIO tooling. The ArduinoIDE
approach may no longer work out of the box; the Prerequisites and ArduinoIDE sections below are
kept for reference but are no longer actively maintained.

### Prerequisites

1. We use a directory structure that will accommodate both techniques.
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
1. Clone the applications (e.g. *StratoCore_RATS*) into *Sketchbook/libraries/*.

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

As mentioned above, the *.pio/* tree and the *src/*.cpp* link, give ArduinoIDE great 
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

In order for edits to the libdeps library to appear in the VSCode Source Control pane, you must
open it as its own repository: View -> Command Palette -> Git: Open Repository, then navigate to
and select the corect _libdeps_ repository. (On macOS, use Shift+Cmd+. to reveal hidden directories,
since _.pio/_ is hidden.)

Once opened, edits will appear in the VSCode Source Control pane, and you can
commit them from here. _BUT if you do a PlatformIO "Clean All",
before committing and pushing, you will lose all of your edits._
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

But there is a very handy port selector, once again at the _bottom_ of VSCode, which
(once again) opens a selector at the _top_ of VSCode. It is initially set to _Auto_;
just change it to the correct port and uploads/monitors will work, and you can leave
multiple Teensies plugged in.

Just make sure that you have the correct one chosen, otherwise you may flash the MCB
with the StratoCore_LPC code and vice versa!
