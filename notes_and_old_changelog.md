# Notes:
1. GBSCSI2 (as of January 2026) does not support powering from TERMPWR in systems with low Vtt. Use the 4-pin connector, with a Molex pigtail if necessary. Examples of machines which may present low Vtt are compact Macs, where TERMPWR is derived from the main 5V rail thru a 1N4001 diode (One can try to mitigate this by replacing the 1N4001 with a Schottky diode of lower Vf).
This exhibits a large forward voltage and may fail to meet SCSI spec. GBSCSI2 is designed with cost and power efficiency in mind, and as such, uses a cheap buck DC-DC converter to supply the board with 3.3V. Minimum input voltage as per the manufacturer's datasheet is 4.2V.
Given the forward voltage of the diodes on GBSCSI2 (about 450mV), and Vtt at TERMPWR having a minimum of 4.25V, this may leave the regulator receiving only about 3.8V. Feeding the regulator less than 4.0V has been reported to result in erratic operation. In that scenario, please power
the board from a separate 5V source as described above. If there is enough demand, a variant employing an LDO can be created. This would, however, waste more power, which is undesirable in laptops - the main use case for which this board was created. A redesign is pending.

2. JLC will no longer solder the Pico for you using their Economic PCBA service. The Standard PCB service has a $25 setup fee. Their Pico prices are not great anyway, so you might as well also solder that on your own, if you wanna save as much as possible. 


# Changelog:
1. PDN redesigned on Hybrid V1.0 boards to provide better ground return paths. V1.0b implements the change and is the first publicly available variant in this repository.

2. v1.0c Hybrid changed to 1.0d, for ground plane repour around 2.5" header keying change in 1.0c. Other 2.5" boards also changed, but as they don't have published gerbers, their revision numbers weren't changed.
Schottky diodes changed in BoM for all boards (JLC P/N C8598 to C82544). This is due to C8598 typically exhibiting too high of a forward voltage.

3. RP2350 boards have been tested by Rabbit Hole Computing's (makers of ZuluSCSI) Alex Perez (many thanks!) and are officially released as validated builds. Suitable firmware available at https://github.com/ZuluSCSI/ZuluSCSI-firmware/releases/tag/v2024.10.11-pico2-beta

4. A Fast Wide SCSI variant was been designed, and abandoned for the entirety of 2025. As of January 2026, the files in the repository are unusable for practical purposes as-is. A redesign is pending.

5. Further changes will no longer be logged here, but in commit history alone. Critical errata will be listed separately.