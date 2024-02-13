# The Main Processor - RasPi4
### Modifications
The main processor of the radio starts out as a standard Raspberry Pi 4. Two modifications have to happen to it. The first is the removal of the USB connectors, the ethernet port, all the pin headers, the CSI and the DSI ports, and the AV port. This is done to lower the height profile of the Pi to just a few millimeters and allows routing the USB connections directly into the TOSR PCB. The second modification is the addition of an SMA antenna connector for Wifi. Since the TOSR's case is aluminum, the Wifi antenna needs to relocated to the exterior.

### Connections
- USB-C - Extended to the exterior of the case with the 5V line cut in order to prevent back supplying power to the connected device
- Pin Header - 5 volt power supply
- USB3.0 - Used for secondary Wifi
- USB2.0 - Used for connection to Teensy and to audio codec
- Ethernet - Broken out to exterior of case

