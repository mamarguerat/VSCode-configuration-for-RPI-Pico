NOTE: Not working yet. I will update this as soon as possible
- [1. MicroPython configuration](#1-micropython-configuration)
  - [1.1. Install MicroPython on the RPI Pico](#11-install-micropython-on-the-rpi-pico)
  - [1.2. Install Python on your machine](#12-install-python-on-your-machine)
  - [1.3. Setup VS Code](#13-setup-vs-code)
  - [1.4. Use VS Code to program RPI Pico](#14-use-vs-code-to-program-rpi-pico)
- [2. C++ configuration](#2-c-configuration)
  - [2.1. Setup VS Code](#21-setup-vs-code)
  - [2.2. Install cMake on your computer](#22-install-cmake-on-your-computer)
  - [2.3. Configure VS Code](#23-configure-vs-code)
    - [2.3.1. Configure CMake](#231-configure-cmake)
  - [2.4. Use VS Code to program RPI Pico](#24-use-vs-code-to-program-rpi-pico)
- [3. C++ configuration using PlateformIO and arduino libraries](#3-c-configuration-using-plateformio-and-arduino-libraries)
  - [3.1. Setup VS Code](#31-setup-vs-code)
  - [3.2. Start a new project](#32-start-a-new-project)

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
**NOT WORKING YET**

## 2.1. Setup VS Code
1. Open VS Code and go to extension tab
2. Search for `cortex` and install *Cortex-Debug* extension
3. Search for `cmake` and install *CMake Tools* extension
4. Search for `c++` and install *C/C++* extension

## 2.2. Install cMake on your computer
1. Go to [cMake website](https://cmake.org/download/), download and install cMake for your machine
   1. During the installation, chech `Add CMake to the system PATH for all users`

## 2.3. Configure VS Code
### 2.3.1. Configure CMake
1. Go to *CMake tools configuration extension settings*
2. Scroll to *Cmake: Configure environment*
3. Click on Add Item and add `PICO_SDK_PATH` and the value is the pico-sdk folder's path
4. Scroll to *Cmake: Generator*
5. Type `NMake Makefiles`

## 2.4. Use VS Code to program RPI Pico
1. In a new VS Code project, enter the command `CMake: Quick Start`, then select `Executable` and the correct kit `GCC for arm-none-eabi`, then enter a project name
2. Click the build button on the bottom of the window

# 3. C++ configuration using PlateformIO and arduino libraries
## 3.1. Setup VS Code

## 3.2. Start a new project

GettingStartedWithMicroPython: https://www.raspberrypi.org/documentation/rp2040/getting-started/#getting-started-with-micropython
GettingStartedWithC: https://www.raspberrypi.org/documentation/rp2040/getting-started/#getting-started-with-c
DownloadPython: https://www.python.org/downloads/
ARMDeveloper: https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads

https://www.element14.com/community/community/raspberry-pi/blog/2021/01/24/working-with-the-raspberry-pi-pico-with-windows
https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads
https://www.electronicshub.org/program-raspberry-pi-pico-with-visual-studio-code/