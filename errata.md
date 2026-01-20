1. v1.0b Hybrid and v1.0 RP2040 boards have the wrong pad deleted for keying pin on 2.5" header - should be 17 instead of 21.

Patch: Do not install/cut pin 17.

Change: Connector rekeyed.

2. Buck converter for 3.3V has too high of a VIN for the combined drops of all diodes in the 5V chain.

Patch: Lower Vf diodes can (and were) substituted as partial mitigation. Users with other needs would need to investigate their own solutions, potentially using an LM1117-3.3V regulator or similar.

Change: Redesign pending. (Jan/26)