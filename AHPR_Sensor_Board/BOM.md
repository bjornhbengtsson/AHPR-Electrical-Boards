# Sensor Board (Rev 2) – Bill of Materials

Parts for one board, taken from [`AHPR_Sensor_Board.SchDoc`](AHPR_Sensor_Board.SchDoc) and [`AHPR_Sensor_Board.PcbDoc`](AHPR_Sensor_Board.PcbDoc). All components sit on the top side. Part numbers link to a Mouser search. A spreadsheet copy for ordering is in [`BOM.csv`](BOM.csv).

**Per board:** 18 placed parts, 12 part numbers, plus R1 and R2 left unfitted.

## Parts to buy

| # | Qty | Designators | Value | Description | Package | Manufacturer | Part number |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 6 | C1, C2, C3, C4, C7, C8 | 100 nF | Ceramic capacitor, 50 V, X7R, 10% | 0603 | Murata | [GRM188R71H104KA93D](https://www.mouser.com/c/?q=GRM188R71H104KA93D) |
| 2 | 1 | C6 | 1 µF | Ceramic capacitor, 10 V, X7R, 10% | 0603 | Murata | [GRM188R71A105KA61D](https://www.mouser.com/c/?q=GRM188R71A105KA61D) |
| 3 | 1 | C5 | 10 µF | Ceramic capacitor, 10 V, X7R, 10% | 0805 | Murata | [GRM21BR71A106KA73L](https://www.mouser.com/c/?q=GRM21BR71A106KA73L) |
| 4 | 1 | FB1 | 220 Ω @ 100 MHz | Chip ferrite bead, 0.05 Ω DCR | 0603 | Murata | [BLM18KG221SN1D](https://www.mouser.com/c/?q=BLM18KG221SN1D) |
| 5 | 1 | R4 | 1 kΩ | Thick-film resistor, 1%, 0.1 W | 0603 | Yageo | [RC0603FR-071KL](https://www.mouser.com/c/?q=RC0603FR-071KL) |
| 6 | 1 | D1 | Green | LED, green | 0603 | Lite-On | [LTST-C191KGKT](https://www.mouser.com/c/?q=LTST-C191KGKT) |
| 7 | 1 | U1 | BMI270 | 6-axis IMU, I2C address 0x68 | LGA-14, 2.5 x 3.0 mm | Bosch Sensortec | [BMI270](https://www.mouser.com/c/?q=BMI270) |
| 8 | 1 | U2 | BMP390 | Barometric pressure and temperature sensor, I2C address 0x76 | LGA-10, 2.0 x 2.0 mm | Bosch Sensortec | [BMP390](https://www.mouser.com/c/?q=BMP390) |
| 9 | 1 | U3 | SAM-M10Q | GNSS module with built-in patch antenna, I2C address 0x42 | 15.5 x 15.5 mm module | u-blox | [SAM-M10Q-00B](https://www.mouser.com/c/?q=SAM-M10Q-00B) |
| 10 | 1 | J1 | 4-pin JST GH | Header, 1.25 mm pitch, right angle, SMD | SMD | JST | [SM04B-GHS-TB(LF)(SN)](https://www.mouser.com/c/?q=SM04B-GHS-TB) |
| 11 | 1 | J2 | 2-pin header | Pin header, 2.54 mm pitch, vertical, gold | Through hole | Samtec | [TSW-102-07-G-S](https://www.mouser.com/c/?q=TSW-102-07-G-S) |
| 12 | 2 | TP1, TP2 | Test point | SMD test point | SMD | Keystone Electronics | [5015](https://www.mouser.com/c/?q=534-5015) |
| 13 | 1 | – | PCB | Bare board, 50 x 50 mm, 2 layers, 1.6 mm FR-4 | – | – | Fab from `AHPR_Sensor_Board.PcbDoc` |

## Do not place

| Qty | Designators | Value | Part number | Notes |
| --- | --- | --- | --- | --- |
| 2 | R1, R2 | 4.7 kΩ, 0603 | [RC0603FR-074K7L](https://www.mouser.com/c/?q=RC0603FR-074K7L) | I2C pull-ups on SDA and SCL. Leave off: the Pi already pulls the bus up with 1.8 kΩ. Fit only with a host that has no pull-ups. |

## Board features (nothing to buy)

| Qty | Designators | What it is |
| --- | --- | --- |
| 4 | TP3, TP4, TP5, TP6 | Bare copper test pads: TP3 GPS TXD, TP4 GPS RXD, TP5 TIMEPULSE, TP6 SAFEBOOT_N |
| 4 | H1, H2, H3, H4 | M2.5 plated mounting holes (2.75 mm hole, 6 mm pad), tied to GND |

## Assembly notes

- **J1 mating cable:** JST GHR-04V-S housing with SSHL-002T-P0.2 crimp contacts. Pins carry 3.3 V, GND, SDA and SCL from power board J15.
- **J2:** shorting the two pins resets the GPS (RESET_N to GND). A 2.54 mm jumper shunt or tweezers works; nothing needs to stay fitted.
- **TP1 / TP2:** +3V3 and GND probe points next to J1.
- **U1, U2:** LGA parts with no exposed leads. Use a stencil and reflow; hand soldering is not practical.
