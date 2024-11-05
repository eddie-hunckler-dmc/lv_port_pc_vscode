# VSCode Simulator project for LVGL

[LVGL](https://github.com/lvgl/lvgl) is written mainly for microcontrollers and embedded systems, however you can run the library **on your PC** as well without any embedded hardware. The code written on PC can be simply copied when your are using an embedded system.

The project is pre-configured for VSCode and should work work on Windows.

This fork includes instructions for building the project with Windows using MSYS2.

## Get started in Windows
### Get the PC project

Clone the PC project and the related sub modules:

```bash
git clone --recursive https://github.com/eddie-hunckler-dmc/lv_port_pc_vscode
```

### Install MSYS2

The first step is to download and install MSYS2 from their [website](https://www.msys2.org/). MSYS2 is a software distribution and building platform for Windows based on MinGW and Cygwin. It provides a Unix-like environment on Windows and a package management system for installing Unix software.

#### Launch MSYS2 MINGW64

After installing MSYS2, open the MSYS2 MINGW64 app from your Start menu. This application provides a terminal where you can install the necessary packages.

In the MSYS2 MINGW64 terminal, you'll need to execute a series of commands to update the package database and install the required packages. Run the following commands one by one:

```bash
pacman -Syu
pacman -S mingw-w64-x86_64-gcc
pacman -S mingw-w64-x86_64-cmake
pacman -S mingw-w64-x86_64-SDL2
pacman -S mingw-w64-x86_64-gdb
```

These commands install the MinGW-w64 GCC (C/C++ compiler), CMake (open-source, cross-platform build system), SDL2 (used for rendering the LVGL graphics on your PC), and GDB (GNU Debugger) packages.

To make the installed tools accessible from the command line, add C:\msys64\mingw64\bin to your system's PATH environment variable. This step ensures that VSCode and other applications can find and use these tools.

## Usage
### Setting Up VSCode

1. Open the project by double clicking on `simulator.code-workspace` or opening it with `File/Open Workspace from File`
2. Install the recommended plugins
3. Click the Run and Debug page on the left, and select `msys64 - (gdb) Launch` from the drop-down on the top.
4. Click the Play button or hit F5 to start debugging.

### CMake

This project uses CMake under the hood which can be used without Visual Studio Code too. Just type these in a Terminal when you are in the project's root folder:

```bash
mkdir build
cd build
cmake ..
make -j
```
