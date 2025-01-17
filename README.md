# Note
This is fork from https://github.com/Wiz-IO/platform-sam-lora.git

I'm adding here some small functionality, like (all is work in progress):

* uploading using JLink
* add definition for wlr089u0
  

---
# Microchip Atmel SAMR34/35 platform for PlatformIO

 **Version 0.1.2** ( [look here, to see if there is something new](https://github.com/Wiz-IO/platform-sam-lora/wiki/VERSION) )
* OS Windows **( for now )** 
* * Baremetal 
* * Arduino ( in process... )
* Board [Microchip SAM R34 Xplained Pro](https://www.microchip.com/DevelopmentTools/ProductDetails/dm320111)
* [Framework Source Codes and Examples](https://github.com/Wiz-IO/framework-sam-lora)
* [Wiki ( read )](https://github.com/Wiz-IO/platform-sam-lora/wiki)

The project is a work in progress and is very beta version - **there may be bugs** 

## Baremetal
* CMSIS
* [ASF ( v 3.47.0.96 )](https://github.com/Wiz-IO/platform-sam-lora/wiki/ASF)
* * [Example: LED Blink](https://github.com/Wiz-IO/framework-sam-lora/tree/master/examples/asf_blink)

## Arduino Core
* Arduino core
* GPIO, ADC, Serial, I2C, SPI, RF
* LoRa & LoraWAN
* Variant: Microchip SAM R34 Xplained Pro
* * [Example: Hello World](https://github.com/Wiz-IO/framework-sam-lora/blob/master/examples/arduino_hello_world/)
* * [Example: OLED from the screenshot](https://github.com/Wiz-IO/framework-sam-lora/tree/master/examples/arduino_oled_i2c)

![sam](https://raw.githubusercontent.com/Wiz-IO/LIB/master/images/sam34-oled.jpg)

[The first steps - youtube](https://www.youtube.com/watch?v=Bhc3n0Go5KI)

[Simple LoRa](https://www.youtube.com/watch?v=3bJiQ3b2fgA)

## Platform Installation

Install VS Code + PlatformIO

PlatformIO - Home - Platforms - Advanced Installation

Paste link: https://github.com/Wiz-IO/platform-sam-lora

## Fast Uninstall
Goto `C:\Users\USER_NAME\.platformio\platforms` and **delete**:
* folder **sam-lora** ( builders )
* folder **framework-sam-lora** ( sources )
* folder **tool-sam-lora** ( uploader )
* folder **toolchain-gccarmnoneeabi** (compiler )

![sam](https://raw.githubusercontent.com/Wiz-IO/LIB/master/images/lorawan-appdata.png)

## Baremetal INI
```ini
[env:samr34xpro]
platform = sam-lora
board = samr34xpro
framework = baremetal
monitor_port = COMx     
monitor_speed = 115200  
```

## Arduino INI
```ini
[env:samr34xpro]
platform = sam-lora
board = samr34xpro
framework = arduino
monitor_port = COMx     
monitor_speed = 115200  
```

## CUSTOM UPLOADERS
The Platform use Microchip SAM R34 Xplained Pro with onboard EDBG uploader 

I don't have a J-LINK, Atmel ICE, stand alone modules and/or custom bootloaders to add more uploaders

The code has a custom experimental "bootload" uploader and you can use it as an entry point for your experimental uploaders

https://github.com/Wiz-IO/platform-sam-lora/blob/master/builder/frameworks/SAMR_FU.py


The main upload entry function is:

**dev_upload(target, source, env)**

https://github.com/Wiz-IO/platform-sam-lora/blob/master/builder/frameworks/arduino-samr34.py#L14

There are conditions for distinguishing the tool used - edit and test...


Create new board, Copy/Paste/Rename and edit boards/samr34xpro.json as experimental board

## Road Map
* Baremetal Uploaders ( now works with atbackend/atprogram )
* Baremetal ASF/CMSIS
* Arduino Bootloader
* Arduino Core
* Arduino Libraries
* Examples

## Thanks to

* [Ivan Kravets ( PlatformIO )](https://platformio.org/)
* Miguel Romani ( TheThings )
* [Comet Electronics](https://www.comet.bg/en/)


>If you want to help / support:   
[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ESUP9LCZMZTD6)
