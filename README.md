CMake Example
=============

This folder shows a bare-bones example of compiling an external firmware
against stm32plus, using CMake and the Ubuntu debian packages from
Launchpad.

    sudo add-apt-repository ppa:mikepurvis/stm32
    sudo apt-get update
    sudo apt-get install stm32plus-headers stm32plus-small-f4-8000000

    mkdir build && cd build
    cmake ..
    make blink.bin

