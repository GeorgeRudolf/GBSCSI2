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

# Notes:
1. GBSCSI2 does not support powering from TERMPWR in systems with low Vtt. Use the 4-pin connector, with a Molex pigtail if necessary. Examples of machines which may present low Vtt are compact Macs, where TERMPWR is derived from the main 5V rail thru a 1N4001 diode (One can try to mitigate this by replacing the 1N4001 with a Schottky diode of lower Vf).
This exhibits a large forward voltage and may fail to meet SCSI spec. GBSCSI2 is designed with cost and power efficiency in mind, and as such, uses a cheap buck DC-DC converter to supply the board with 3.3V. Minimum input voltage as per the manufacturer's datasheet is 4.2V.
Given the forward voltage of the diodes on GBSCSI2 (about 450mV), and Vtt at TERMPWR having a minimum of 4.25V, this may leave the regulator receiving only about 3.8V. Feeding the regulator less than 4.0V has been reported to result in erratic operation. In that scenario, please power
the board from a separate 5V source as described above. If there is enough demand, a variant employing an LDO can be created. This would, however, waste more power, which is undesirable in laptops - the main use case for which this board was created. Comments are welcome via the Issues tab.

2. JLC will no longer solder the Pico for you using their Economic PCBA service. The Standard PCB service has a $25 setup fee. Their Pico prices are not great anyway, so you might as well also solder that on your own, if you wanna save as much as possible.


# Changelog/Errata:
1. PDN redesigned on Hybrid V1.0 boards to provide better ground return paths. V1.0b implements the change and is the first publicly available variant in this repository.

2. v1.0b Hybrid and v1.0 RP2040 boards have the wrong pad deleted for keying pin on 2.5" header - should be 17 instead of 21.

Patch: Do not install/cut pin 17.

Change: Connector rekeyed.

3. v1.0c Hybrid changed to 1.0d, for ground plane repour around 2.5" header keying change in 1.0c. Other 2.5" boards also changed, but as they don't have published gerbers, their revision numbers weren't changed.
Schottky diodes changed in BoM for all boards (JLC P/N C8598 to C82544). This is due to C8598 typically exhibiting too high of a forward voltage.

4. RP2350 boards have been tested by Rabbit Hole Computing's (makers of ZuluSCSI) Alex Perez (many thanks!) and are officially released as validated builds. Suitable firmware available at https://github.com/ZuluSCSI/ZuluSCSI-firmware/releases/tag/v2024.10.11-pico2-beta