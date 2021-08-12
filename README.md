# Helium Hardware Definitions

This repository contains the python file that contains a GPIO map for all of the different hardware combinations to be supported by the Nebra Helium Hotspot Software.

All numbers below are their GPIO / BCM Numbers, not physical pin numbers.

Note: Light hotspot software will also work on all listed as variant "full"

# Nebra Hotspots

| Model | ENV Identifier | SPI Bus | Reset Pin | Status LED | Button |Type | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Nebra Indoor Hotspot Gen 1 | NEBHNT-IN1 | 1.2 | 38 | 25 | 26 | Full | CM3 based |
| Nebra Outdoor Hotspot Gen 1 | NEBHNT-OUT1 | 1.2 | 38 | 25 | 24 |  Full | CM3 based |
| Nebra Pi 0 Light Hotspot S | NEBHNT-LGT-ZS | 1.2 | 22 | 24 | 23 |  Light | SPI Based Ethernet |
| Nebra Pi 0 Light Hotspot X | NEBHNT-LGT-ZX | 1.2 | 22 | 24 | 23 |  Light |  USB Based Ethernet |
| Nebra Beaglebone Light Hotspot | NEBHNT-BBB | 1.0 | 60 | 31  | 30  |  Light | In Planning |
| Nebra Pocket Beagle Light Hotspot | NEBHNT-PBB | 1.0 | 60 | 31 | 30 | Light | In Planning |
| Nebra Hotspot HAT RockPi4 | NEBHNT-HHRK4 | 1.0 | 149 | 156 | 154 |  Full | In Planning |
| Nebra Hotspot HAT RPi | NEBHNT-HHRPI | 0.0 | 22 | 24 | 23 |  Full |  Should be compatible with 3+ & 4 |
| Nebra Hotspot HAT RPi LIGHT | NEBHNT-HHRPL | 0.0 | 22 | 24 | 23 |  Light |  Light is compatible with all 40 pin headers |
| Nebra Hotspot HAT Tinkerboard 2 | NEBHNT-HHTK | 2.0 | 167 | 163 | 162 |  Full |  Light would be compatible on TK1 |

# Third Party Hotspots

We may be adding in support for other vendor's hotspots to use our software soon. Here are the variables for those.

These would also depend on their SOCs being supported by Balena.

| Model | SOC/SBC | ENV Identifier | SPI Bus | Reset Pin | Status LED | Button |Type | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Rak Hotspot Miner | BCM2711 (Pi4 2gb RAM)  | COMP-RAKHM |  |  |   |   | Full | Only Compatible with V2 hotspots with ECC Key. |
| OG Helium Hotspot | BCM2711 (Pi4 2gb RAM) | COMP-HELIUM |  |  |   |   | Full |  |
| Syncrobit Hotspot 1 (Pi) |  |  |  |  |   |   | Full |  |
| Syncrobit Hotspot 2 (RK) |  |  |  |  |   |   | Full |  |
| Bobcat Miner 300 |  |  |  |  |   |   | Full |  |
| Sensecap M1 | BCM2711 (Pi4 2gb RAM)  | COMP-SENSECAP |  |  |   |   | Full |  |

# DIY Hotspots

The following DIY options are also supported for light hotspot software only.

Please note, DIY Hotspots do not earn HNT.

| Model | SOC/SBC | ENV Identifier | SPI Bus | Reset Pin | Status LED | Button |Type | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pi Supply IoT LoRa Gateway HAT | RPi | DIY-PISLGH | 0.0 | 22 |   |   | Light | Any pi with 40 pin header |
| RAK2287 | RPi | DIY-RAK2287 | 0.0 | 17 |   |   | Light | Any pi with 40 pin header |


# Install

This package is automatically built and published to [our PyPI repo](https://pypi.org/project/hm-hardware-defs) using GitHub Actions. Installing the package is as simple as:

```
pip install hm-hardware-defs
```

You can also install a specific version using:

```
pip install hm-hardware-defs==0.1.4
```

# Usage

You can use the hardware definitions within your project by importing the package into your python script as follows:

```python
from hm_hardware_defs.variant import variant_definitions
```

# Important Notes

This package is used in a number of Nebra software repos:
- [hm-pktfwd](https://github.com/NebraLtd/hm-pktfwd/)
- [hm-config](https://github.com/NebraLtd/hm-config/)
- [hm-diag](https://github.com/NebraLtd/hm-diag/)

# Contributing

If there is hardware that you would like to be supported that is not listed here, please complete one of the following:

* Create an issue on this repository which has the name of the Hotspot, or DIY solution. With at a minimum a link to a pinout of the device and which SBC it is to be used with.
* Fork this repository and add the device to the array in variant_definitions, update the table above and then create a pull request.
