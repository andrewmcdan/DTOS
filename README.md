# Tactical Open Source Radio (TOSR)
## Purpose
The TOSR (tosser) project aims to create an advanced, open-source communications platform designed specifically for use by military, paramilitary, civilian militia, and emergency services personnel who lack the backing of well-financed organizations. This initiative seeks to provide an affordable alternative to expensive proprietary radios, democratizing access to high-quality tactical communication tools like the Persistent Systems MPU5 or the Harris Falcon III. While commercial systems can cost upwards of $5,000 to $20,000 (USD) and more, the goal of the TOSR radio is to be buildable for under $500, depending on the how the case is made (machined aluminum, 3D printed ABS, etc).

## Target Audience
- Military
- Paramilitary
- Civilian Militia
- Emergency Services Personnel

## Technical Specifications
### Core Components
- Raspberry Pi 4B with modifications to remove through-hole connectors for a lower profile.
- [WiFi Module]() - The RasPi's integrated WiFi will be used for connecting to another unit, and the a secondary WiFi module is used for an AP for other units to connect to. Currently evaluating types and styles of modules to use.
- Teensy 4.1 microcontroller: This will handle communication between the RasPi and the other modules along with encoding data into audio signals.
### Radios
- VHF/UHF: 3 UHF/VHF pairs of SA818 modules, for voice and data over short range
- 900MHz LoRa: Long range data, low bandwidth, for telemetry (GPS, etc)
- WiFi 2.4GHz and 5GHz: IP comms
- Bluetooth: Cellphone interface
- GPS
### Ports / Connectors
- K1 connector for headsets
- USB-C for charging and data
- Ethernet

## Future Functionalities
- Support for IP devices (laptops, cellphones via WiFi)
- Full digital voice
- Encryption
- Interoperability with standard two-way radios
- Weather radio reception

Some functionality can be added in the future through software updates, and this radio will be designed with these future features in mind. 

## Design Considerations
- Durability: The case will be machined from billet billet aluminum for ruggedness and heat dissipation.
- Dimensions: Approximately 3in x 1.6in x 6in (excluding the battery). The battery will extend the length by an additional 4 inches.

## Challenges
The primary challenge lies in the solo development phase, which requires extensive work to reach a working prototype. The project's success depends on effective time management and potentially expanding the development team to accelerate progress.

## Sub-Projects
The TOSR project is broken down into various sub-projects/repos in order to maintain organization. This repo contains the specs that each one is based on. As the project progresses, the sub-projects may progress beyond the what has been specified in the specs file here. The specs files are meant as the starting point for getting each sub-project going.

### [Schematics](https://github.com/andrewmcdan/TOSR-Schematics)
This repo will contain the schematics, PCB designs, etc. The most up-to-date schematics can be found [here](https://oshwlab.com/andrewmcdan/raspi-cm4-carrier).

### Raspberry Pi Software
The Raspberry Pi runs a standard Raspberry Pi OS Lite image with the following applications running as daemons:
- [WiFi / network manager](https://github.com/andrewmcdan/TOSR-RPi-network-manager)
- [Audio decoder](https://github.com/andrewmcdan/TOSR-RPi-Audo-Decoder)
- [Module Manager](https://github.com/andrewmcdan/TOSR-RPi-Module-Manager)

The daemons can be installed using the script (not created yet).sh from this repo which will download the necessary files and install them.

### [Teensy 4.1](https://github.com/andrewmcdan/TOSR-Teensy)
The software for the Teensy, which handles most of the low level management of the hardware (outside of the RasPi), should be compiled and loaded using Arduino. Dependencies are noted in the repo.

### [LoRa Module](https://github.com/andrewmcdan/TOSR-LoRa-Feather-M0)
The LoRa module is supplied by Adafruit Industries and includes a Feather M0 processor. Compile and load using Arduino. See repo for dependencies. 

### [Android App]()
Companion Android app for viewing peer's locations on a map and configuring the TOSR.

# Contributing
Contributions are welcomed from developers, designers, engineers, and enthusiasts across the board. For more information on contributing, please see contributing.md, along with the respective sub-project repositories.

# Thoughts and Possibilities
The [M17 project](https://m17project.org/) looks like a good foundation on which this project can build. Further investigation required. 

[Ribbit Radio](https://www.ribbitradio.org/#/) may be another good source to look at.

At some point, once I have working prototypes, I would like to start making kits to sell on Tindie so that folks can make their own TOSR without needing to source the PCB(s) and case.