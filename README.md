stm32plus CMake Example
=======================

[![Build Status](https://travis-ci.org/mikepurvis/stm32plus-example.svg)](https://travis-ci.org/mikepurvis/stm32plus-example)

This folder shows a bare-bones example of compiling a firmware
against [stm32plus][1], using CMake and the [debian packages from
Launchpad][2], available for Trusty and Precise.

    sudo add-apt-repository ppa:mikepurvis/stm32
    sudo apt-get update
    sudo apt-get install stm32plus-headers stm32plus-small-f4-8000000

    mkdir build && cd build
    cmake ..
    make blink.bin

To load the generated firmware onto your Discovery kit, use OpenOCD
or dfu-util (instructions forthcoming).

[1]: https://github.com/andysworkshop/stm32plus
[2]: https://launchpad.net/~mikepurvis/+archive/ubuntu/stm32

