# GBSCSI2
Affordable SCSI Disk Emulator - upgrade over the original GBSCSI

Herein are the design files for all variants of GBSCSI2 in KiCad 7 format. The hardware in this repository is licensed CERN OHL-S V2, the full terms of which can be found at https://ohwr.org/cern_ohl_s_v2.pdf and https://ohwr.org/cern_ohl_s_v2.txt.

With thanks to https://decromancer.ca for sponsoring this project; wohali, tr0n, compu85, sabur and luigi30 for testing; and the rest of UHF for their continued enthusiasm and support.

# HOW TO:
1. Buy board from decromancer
2. It arrives at your doorstep ready to use

OR

1. Get assembled boards using the files in this repository
2. Solder header of your choice
3. (Except for RP2040 version, or if ordering Pico from JLC) Solder RPi Pico - use Pico-W if you want DaynaPORT capabilities for a Mac
4. Go to https://github.com/ZuluSCSI/ZuluSCSI-firmware and grab the Pico/Pico_DaynaPORT version of the latest release and flash to the board by connecting via USB while holding BOOTSEL (or toggling the boot dip switch for RP2040)

# Changelog/Errata:
1- PDN redesigned on Hybrid V1.0 boards to provide better ground return paths. V1.0b implements the change and is the first publicly available variant in this repository.

2- v1.0b Hybrid and v1.0 RP2040 boards have the wrong pad deleted for keying pin - should be 17 instead of 21.
Patch: Do not install/cut pin 21.
Change: Connector rekeyed.
