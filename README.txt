LED BREATHE (code adapted from adafruit's strndtest example)

PROJECT WORKFLOW
Board - Adafruit STM32F405 Feather
IDE - Arduino (w/ STM32duino add-on)
Compiler - arm-none-eabi-gcc
Programmer - J-Link Commander in SWD mode using J-Link mini edu
Debugger - N/A

PURPOSE
The main goal of this project was to get acquainted with the various STM32 toolchains, try different ones out, and ultimately settle on a programming workflow that works for me. The Arduino IDE allows for the flexibility of extremely user friendly libraries in a familiar setting, but you can also manipulate registers and write your own libraries if you like which is nice. I tried to use the on-board dfu boot loader to flash the board, but ran into issues where it wasn't being recognized by any computer I connected it to. I also tried using STM32CubeProg, but had trouble navigating the GUI. Eventually I settled on programming through the command line with J-link. I like this approach because it helps me understand what's going on under the hood rather than simply pressing "Build" in a more feature rich IDE. While I think it would be better to eventually move over to something more professional like Keil or STM32CubeIDE, programming via J-Link Commander was a great learning experience. It really helped me brush up on my command line and refreshed me on some scripting basics.

The code itself is super simple. It just indefinitely "breathes" the on-board Neopixel LED in Cyan coloring. Again the main focus of this project was toolchain workflow so the code wasn't meant to be anything really special.

EXPLANATION OF INCLUDED FILES
strandtest.ino - Arduino source code adapted from the adafruit example
strandtest.ino.FEATHER_F405.bin - Binary exported from Arduino
FeatherFlash - zsh command line executable used to automate/speed up the flashing process. Simply run this and follow the prompts to flash binary to MCU
CommandFile.jlink - A set of J-Link commands referenced by FeatherFlash for easy flashing