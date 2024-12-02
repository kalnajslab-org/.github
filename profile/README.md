# Kalnaslab-org
Organization for the LASP Kalnajs Team

## Instrument Repository Dependencies

### Laser Particle Counter (LPC)
Main Board:
1. StratoCore_LPC
2. StratoCore
3. StrateoXML
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

With a few workarounds, the kalnajslab-orb repositories can be used in either environment. A
workflow is documented here which describes how to do this.

### Prerequisites

1. Create a directory structure that will accomodate both techniques. ArduinioIDE is the one that
is most particular. Create a top level directory, which will be your *Sketchbook* location.
You may already have one, typically *~/Documents/Arduino/*. Add a *libraries* sub-directory:
```sh
<Sketchbook>/ --
           |
           -> libraries/
```
1. Run the ArduinoIDE. Open the *Settings*, and set the Sketchbook path to your
   *Sketchbook* directory.
1. Our application repositories will be checked out into the *Sketchbook* directory.
1. Libraries will be located in the *libraries/* directory. These can be populated
   from any of:
   - The ArduinoIDE library manager
   - `git clone` of one of our repositories
   - Unzipping of a library file.
1. Clone the application (e.g.*StratoCore_RATS*) to the *<Sketchbook>* directory.

### ArduinoIDE

There are a couple of PlatformIO items which will cause the ArduinoIDE to
go bonkers:
1. Remove the *main.cpp* link that you may have made for working with PlatformIO
2. Remove the *.pio* directory.

Now you should be able to run the ArduinoIDE, open the *.ino* file, and build/upload/monitor the
application.

### PlatformIO

The main program for our application is the *.ino* file at the top level of the
repository. PlatformIO doesn't expect here to be a source file here, and so it will
not compile it, leading to link errors. So we create a link which makes it visible 
to the dependenct scanner (e.g.):

```sh
ln -s StratoCore_RATS.ino src/main.cpp
```

Library requirements are specified in *platformio.ini*, and they are
fetched automagically, so that *libraries/* is ignored by PlatformIO.

PlatformIO creates the *.pio/* tree to hold all of the build artifacts.
This, along with *src/main.cpp*, gives ArduinoIDE great indigestion. 

So, when we wantto use the ArduinoIDE, ***we simply delete _src/main.cpp_ and _.pio_/***.

