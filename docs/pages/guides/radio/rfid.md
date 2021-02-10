---
title: 0x05 - Analyzing RFID
parent: Radio Hacking
grand_parent: Hacking Guides
has_children: false
nav_order: 4
---

# Analyzing RFID

[RFID](https://en.wikipedia.org/wiki/Radio-frequency_identification)

Passiv RFID tags are powered by the RFID reader and are short range.

Active RFID tags are battery-powered and can reach much further, like 100m.

* standards
    * ISO/IEC 18000
    * ISO/IEC 29167
    * ISO/IEC 14443
        * MIFARE?
    * ISO/IEC 20248
    * [ISO/IEC JTC 1/SC 31](https://en.wikipedia.org/wiki/ISO/IEC_JTC_1/SC_31)

* rewritable RFID tags?
    * <https://www.researchgate.net/post/Are-there-rewritable-passive-RFID-tags>
    * blank cards <https://www.amazon.com/Writable-Frequency-13-56mhz-Changeable-Rewritable/dp/B07MJ7JNVV>
* <https://hackmethod.com/hacking-mifare-rfid/?v=f003c44deab6>
* <https://hackmethod.com/hacking-mifare-rfid-2/?v=f003c44deab6>
* [Mifare](https://en.wikipedia.org/wiki/MIFARE)
    * mifare classic
        * example: yale v2n
    * mifare plus
    * mifare ultralight
    * mifare desfire
        * example: yale doorman L3
* [ISO/IEC 14443](https://en.wikipedia.org/wiki/ISO/IEC_14443)
    * ISO/IEC 14443-1:2018 Part 1: Physical characteristics
    * ISO/IEC 14443-2:2016 Part 2: Radio frequency power and signal interface
    * ISO/IEC 14443-3:2018 Part 3: Initialization and anticollision
    * ISO/IEC 14443-4:2018 Part 4: Transmission protocol
* [Mifare Classic Offline Cracker (MFOC)](https://github.com/nfc-tools/mfoc) (TODO only older MIFARE?)
* <https://cs.uwaterloo.ca/~oabari/Papers/Mobicom18a.pdf>
* <https://resources.bishopfox.com/resources/tools/rfid-hacking/attack-tools/>
* <https://www.rfidsupply.se/>
* <https://www.youtube.com/watch?v=nn-nuhAByRk>
    * RC522 RFID (MFRC522?)
* <https://www.researchgate.net/publication/318235597_RFID_Eavesdropping_Using_SDR_Platforms>
* [NFC](https://en.wikipedia.org/wiki/Near-field_communication)
* frequencies
    * 125khz ([older?](https://www.ict.co/Choosing-Card-Technology))
        * "proximity cards".
    * 13.56mhz
        * "smart cards". MIFARE.
        * yale doormand L3

* older yale v2n
    * <https://forum.dangerousthings.com/t/yale-doorman-v2n-cracking-by-iceman/5181>

* readers
    * MFRC522 with more stuff <https://www.elfa.se/sv/mfrc522-mini-rfid-unit-m5stack-u031/p/30172532>
        * [manual](https://www.elfa.se/Web/Downloads/_t/ds/U031_eng_tds.pdf)
        * 58sek (no moms)
        * 13.56 MHz
        * ISO14443A, MIFARE and NTAG
    * <https://www.kjell.com/se/produkter/el-verktyg/arduino/moduler/rfid-lasare-for-arduino-p87046>

* <https://www.youtube.com/watch?v=N0p3_ES2dBU>
* <https://github.com/miguelbalboa/rfid>
* <https://www.arduino.cc/reference/en/libraries/mfrc522/>
* <https://lastminuteengineers.com/how-rfid-works-rc522-arduino-tutorial/>
* <https://www.reddit.com/r/hacking/comments/148nby/android_nfc_and_rfid_door_hack/>
* <https://www.reddit.com/r/hacking/comments/9vttmw/mifare_desfire/>
* <https://sovsecurity.com/how-your-access-control-may-be-hacked/>
* <https://www.nxp.com/docs/en/data-sheet/MF3DX2_MF3DHX2_SDS.pdf>
* <https://en.wikipedia.org/wiki/MIFARE#MIFARE_DESFire_attacks>
* <https://www.sweclockers.com/forum/trad/1472231-kopiera-sl-kort-till-ett-eget-nfc-kort>
* [proxmark3](http://www.proxmark.org/) [code](https://github.com/Proxmark/proxmark3)
* NFC tools (android app)
* <https://github.com/emsec/ChameleonMini>
* <https://www.youtube.com/watch?v=06nal8BuB2w> (in german)
    * a lot of good information!?
* <http://open-nfc.sourceforge.net/wp/>
* <https://www.youtube.com/watch?v=pI7k5b0yhb0>
* <https://www.youtube.com/watch?v=ZSrOq40z1i8>
* [libnfc](https://github.com/nfc-tools/libnfc)
* [libfreefare](https://github.com/nfc-tools/libfreefare)
* <http://nfc-tools.org/index.php/Main_Page>
* <https://docs.google.com/spreadsheets/d/1EvKvov0tJTwuF-q75HYxZNBQFGCwkdnsjWE2-tCocVU/edit#gid=0>
* <https://www.reddit.com/r/RFID/comments/jxtm6b/proxmark3_vs_chinamark3_vs_chameleon_mini/>
