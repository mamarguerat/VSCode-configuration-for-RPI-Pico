NOTE: Not working yet. I will update this as soon as possible
- [1. MicroPython configuration](#1-micropython-configuration)
  - [1.1. Install MicroPython on the RPI Pico](#11-install-micropython-on-the-rpi-pico)
  - [1.2. Install Python on your machine](#12-install-python-on-your-machine)
  - [1.3. Setup VS Code](#13-setup-vs-code)
  - [1.4. Use VS Code to program RPI Pico](#14-use-vs-code-to-program-rpi-pico)
- [2. C++ configuration](#2-c-configuration)
  - [2.1. Install softwares and compilers](#21-install-softwares-and-compilers)
    - [2.1.1. GCC compiler](#211-gcc-compiler)
    - [2.1.2. Install cMake on your computer](#212-install-cmake-on-your-computer)
    - [2.1.3. Install C++ for Visual Studio](#213-install-c-for-visual-studio)
  - [Download and configure PICO SDK](#download-and-configure-pico-sdk)
  - [2.2. Setup VS Code](#22-setup-vs-code)
  - [2.3. Configure VS Code](#23-configure-vs-code)
    - [2.3.1. Configure CMake Tools](#231-configure-cmake-tools)
  - [2.4. Use VS Code to program RPI Pico](#24-use-vs-code-to-program-rpi-pico)
- [3. C++ configuration using PlateformIO and arduino libraries](#3-c-configuration-using-plateformio-and-arduino-libraries)
  - [3.1. Setup VS Code](#31-setup-vs-code)
  - [3.2. Install drivers](#32-install-drivers)
  - [3.3. Start a new project](#33-start-a-new-project)
  - [3.4. Build and upload](#34-build-and-upload)

# 1. MicroPython configuration
## 1.1. Install MicroPython on the RPI Pico
1. Go to [rp2040 documentation site](https://www.raspberrypi.org/documentation/rp2040/getting-started/#getting-started-with-micropython) and download U2F file
2. Connect the pico to your computer while pressing on `BOOTSEL` button
3. Copy the U2F file on the Pico's filesystem
![Install MicroPython on PRI Pico](Images/MicroPython-FINAL.gif)

## 1.2. Install Python on your machine
1. Go to [Python website](https://www.python.org/downloads/) and download the last version of Python
2. Install the downloaded file on your machine. Make sure to add python to PATH
![Add python to PATH](Images/Capture%20d’écran%202021-05-12%20083257.jpg)

## 1.3. Setup VS Code
1. Open VS Code and go to extension tab
2. Search for `pico` and install *Pico-Go* extension `chriswood.pico-go`
3. Search for `python` and install *Python* extension `ms-python.python`

## 1.4. Use VS Code to program RPI Pico
1. In a new VS Code project, enter the command `Pico-Go > Configure Project`
2. Connect your RPI Pico with USB. The terminal will tell you on wich COM port your connected
3. You can create a new `.py` file and write code
4. There is buttons on the bottom of the window to run or upload code and connect the board to VS Code
![Run project](Images/Capture%20d’écran%202021-05-12%20082523.jpg)

A project example can be found in the MicroPython branch of this repository.

# 2. C++ configuration
Make sure to have python installed (Step [1.2. Install Python on your machine](#12-install-python-on-your-machine))
A video can be found on [YouTube](https://youtu.be/mUF9xjDtFfY)

## 2.1. Install softwares and compilers
### 2.1.1. GCC compiler
1. Go to [ARM website](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) and download the last version
2. Install the compiler. Make sure to check `Add path to environment variable`
![Add path to environment](Images/Capture%20d’écran%202021-05-12%20101716.jpg)

### 2.1.2. Install cMake on your computer
1. Go to [cMake website](https://cmake.org/download/), download and install cMake for your machine
2. During the installation, chech `Add CMake to the system PATH for all users`
![Add CMake to the system PATH](Images/Capture%20d’écran%202021-05-12%20101908.jpg)
### 2.1.3. Install C++ for Visual Studio
1. Go to [Microsoft website](https://visualstudio.microsoft.com/fr/downloads/) and scroll to "Build Tools for Visual Studio 2019" and click on Download
2. Run the file and select *C++ build tools* and click install

## Download and configure PICO SDK
1. Go to the [GitHub repository](https://github.com/raspberrypi/pico-sdk) and download the repository
2. Go to the [GitHub examples repository](https://github.com/raspberrypi/pico-examples) and download the repository
3. Put these repositories in a folder on your machine, for example `C:\Pico`
4. Open a Developer Command Prompt, go to your folder et add pico-skd to PATH
```
cd C:\Pico
setx PICO_SDK_PATH "..\..\pico-sdk"
```

## 2.2. Setup VS Code
1. Open VS Code and go to extension tab
2. Search for `cortex` and install *Cortex-Debug* extension `marus25.cortex-debug`
3. Search for `cmake` and install *CMake Tools* extension `
ms-vscode.cmake-tools`
4. Search for `c++` and install *C/C++* extension `ms-vscode.cpptools`

## 2.3. Configure VS Code
### 2.3.1. Configure CMake Tools
1. Go to *CMake tools configuration extension settings*
2. Scroll to *Cmake: Configure environment*
3. Click on Add Item and add `PICO_SDK_PATH` and the value is the pico-sdk folder's path `..\..\pico-sdk`
4. Scroll to *Cmake: Generator*
5. Type `NMake Makefiles`

## 2.4. Use VS Code to program RPI Pico
1. In a new VS Code project, enter the command `CMake: Quick Start`, then select `Executable` and the correct kit `GCC for arm-none-eabi`, then enter a project name
2. Click the build button on the bottom of the window

# 3. C++ configuration using PlateformIO and arduino libraries
Make sure to have python installed (Step [1.2. Install Python on your machine](#12-install-python-on-your-machine))
## 3.1. Setup VS Code
1. Open VS Code and go to extension tab
2. Search for `PlatformIO` and install *PlatformIO IDE* extension `platformio.platformio-ide`

## 3.2. Install drivers
1. Go to [Zadig website](https://zadig.akeo.ie/) and download Zadig
2. Open Zadig and select `RP2 Boot (Interface 1)` and the `WinUSB` driver
3. Click on Install Driver
![Install driver](Images/Capture%20d’écran%202021-05-12%20100915.jpg)

## 3.3. Start a new project
1. Open the PIO Home window and click on `New Project`
![Open PIO Home](Images/Capture%20d’écran%202021-05-12%20090233.jpg)
2. Choose a name for your project and select your board and the Arduino framework
![New PIO Project](Images/Capture%20d’écran%202021-05-12%20090459.jpg)

## 3.4. Build and upload
1. Before uploading a project for the first time. Add 2 lines to `platformio.ini` file
On Windows use the drive letter when the pico is connected in BOOTSEL mode
On MacOS use `Volumes/RPI-RP2`
On Linux use the path where the volume is mounted
```
upload_port = E:\
upload_protocol = picotool
```
2. To buil or upload your project, the tasks can be found in the PlatformIO plug-in
![Build or Upload project](Images/Capture%20d’écran%202021-05-12%20100221.jpg)