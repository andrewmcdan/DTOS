# Digital Tactical Open Source (DTOS) Radio
## Purpose
The DTOS radio project aims to create an advanced, open-source communications platform designed specifically for use by military, paramilitary, civilian militia, and emergency services personnel who lack the backing of well-financed organizations. This initiative seeks to provide an affordable alternative to expensive proprietary radios, democratizing access to high-quality tactical communication tools like the Wave Radio MPU5 or the Harris Falcon III. 

## Target Audience
- Military
- Paramilitary
- Civilian Militia
- Emergency Services Personnel

## Technical Specifications
### Core Components
- Processor: Raspberry Pi 4B with modifications to remove through-hole connectors for a lower profile.
- System Management: Teensy 4.1 microcontroller.
### Radios
- VHF/UHF: 3 UHF/VHF pairs of SA818 module, for voice and data over short range
- 900MHz LoRa: Long range data, low bandwidth
- WiFi 2.4GHz and 5GHz: IP comms
- Bluetooth: Cellphone interface
- GPS
### Ports / Connectors
- K1 connector for headsets
- USB-C for charging and data.

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
This project is broken down into various sub-projects/repos in order to maintain organization.
### Raspberry Pi Software
The Raspberry Pi runs a standard Raspberry Pi OS Lite image with the following applications running as daemons:
- [WiFi / network manager]()
- [Audio decoder]()

The daemons can be installed using the script (not created yet).sh from this repo which will download the necessary files and install them.

### [Teensy 4.1]()
The software for the Teensy, which handles most of the low level management of the hardware (outside of the RasPi), should be compiled and loaded using Arduino. Dependencies are noted in the repo.

### [LoRa Module]()
The LoRa module is supplied by Adafruit Industries and includes a Feather M0 processor. Compile and load using Arduino. See repo for dependencies. 

### [Android App]()
Companion Android app for viewing peer's locations on a map and configuring the DTOS.

# Contributing
Contributions are welcomed from developers, designers, engineers, and enthusiasts across the board. For more information on contributing, please see contributing.md, along with the respective sub-project repositories.