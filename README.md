![](./images/opensourcehw-100x82.png)

-----

# Kelvin NTC10K

This module is part of the [VSCP project](https://www.vscp.org).  It is free to use, modify and sell. The only thing we kindly ask is that improvements and extensions are contributed back to the project (at your will). This to make the project better for everyone. All design files is licensed under the [MIT license](https://en.wikipedia.org/wiki/MIT_License).

![](./images/kelvin11.png)

In the repository you find the development files for the Kelvin NTC10K module. The project is also the base for a VSCP implemention on a Microchip 18F PIC device together with the [Paris Relay Module](https://github.com/grodansparadis/can4vscp_paris).

Kelvin NTC10K is a temperature module that can handle six temperature sensors. One internal and five external.

The full documentation for the module can be found [here](http://grodansparadis.github.io/can4vscp_kelvin_ntc10k/#/).

---

## Steps you should go through to adopt this file for your own VSCP project.

  * The frequency for your system may be different. This will affect the CAN bit rate settings which are defined in the biginning of the can18f.c file. Here you also find the filter/mask  defines if you need to change these. Timer0 is used as a 1 ms timer for the VSCP functionality. You should adopt the timer reload value in the main.h file to your system.

  * The GUID (Glocal Unique ID) is defined in the beginning of vscp.c This number should be different for each piece of equiment you produce. Regard it is as the device serial number. It can be moved to EEPROM if that is found more convinient. In that case the vscp_rcv_readreg  procedure in vscp.c also has to be changed.

  * The device URL is defined in the beginning of the vscp.c file. This is an URL without the initial "http://" that should point to a XML file that give information about your piece of equipment.

  * The manufacturer id is also defined in the beginning of the vscp.c file. You can use this id in any way you like.

In addition to this you may use different pins for the INIT button (RC0 today) and the status LED (RC1) today. Changes affect the main interrupt vector.





