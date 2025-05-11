---
title: Architecture
layout: home
nav_order: 12
---

# Architectural Overview

## Entry Point

The entry point is `main.c` located in `Core/Src/main.c` which contains the generated STM32 initialization C code. 
It then calls `autopilot_main_c()` in the C++ wrapper `Core/Src/autopilot_main.cpp` to run the C++ autopilot code.

## File Structure

The platform independent autopilot code is stored in `Autopilot` folder. The rest of the file is platform specific for low-level tasks such as interfacing with sensors using SPI.

## Control Flow

Every module has an `update()` function (see base class `Autopilot/module.h`). In `Autopilot/autopilot.h` and `Autopilot/autopilot.cpp`, every module is initialized. The function `void Autopilot::setup()` initializes the hardware and sets the main task to `void Autopilot::main_task()`. The function `void Autopilot::main_task()` then is run continuously at a fixed update rate which calls the `update()` function from each module.
