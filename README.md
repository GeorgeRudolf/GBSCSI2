# GBSCSI2
Affordable SCSI Disk Emulator - upgrade over the original GBSCSI

NOTE: Above all, these boards were initially designed as a hack to satisfy my own personal needs. With that said, they've been tested fairly extensively. Please read this entire README.

Herein are the design files for all variants of GBSCSI2 in KiCad 7 format, being migrated to KiCad 9. The hardware in this repository is licensed CERN OHL-S V2, the full terms of which can be found at https://ohwr.org/cern_ohl_s_v2.pdf and https://ohwr.org/cern_ohl_s_v2.txt.

With thanks to [The Decromancer](https://decromancer.ca/) for sponsoring this project; wohali, tr0n, compu85, sabur and luigi30 for testing; and the rest of UHF for their continued enthusiasm and support. Also to [Rabbit Hole Computing](https://www.rabbitholecomputing.com/) for their continued maintenance of the ZuluSCSI firmware that makes these boards complete, and further testing and collaboration on this project.

# HOW TO:
1. Buy board from decromancer or [Emmy Bear Retro](https://retro.emmybear.shop)
2. It arrives at your doorstep ready to use

OR

1. Get assembled boards using the files in this repository
2. Solder header of your choice
3. (Except for RP2040 version, or if ordering Pico from JLC) Solder RPi Pico - use Pico-W if you want DaynaPORT capabilities for a Mac
4. Go to https://github.com/ZuluSCSI/ZuluSCSI-firmware and grab the Pico/Pico_DaynaPORT version of the latest release and flash to the board by connecting via USB while holding BOOTSEL (or toggling the boot dip switch for RP2040)


# The (very important) details:

1. GBSCSI2 is being moved to a revised hierarchical design that allows for modularity and ease of customization, while maintaining uniformity. The whole project is considered WIP - this warning will be removed once things are tested. Previous versions have been moved to an archive folder. More about them below.

2. The archived Wide SCSI variants are BROKEN. They're incomplete and not usable. 
Rabbit Hole Computing has forked these designs, corrected their flaws and finished the implementation in a manner compatible with standard ZuluSCSI firmware. This fork is now available at https://github.com/ZuluSCSI/ZuluSCSI-Ultra-Wide-OSHW-RP2350B.

3. The variants tagged "untested" are exactly that. I've never personally made boards from them. Use at your own risk.

4. For changes and errata, see the relevant files in the repo.


