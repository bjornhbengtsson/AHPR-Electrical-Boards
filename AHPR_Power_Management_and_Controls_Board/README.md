# AHPR Lotus Power Management and Controls Board (Rev 2)

Raspberry Pi 3 A+ HAT that handles battery input and protection, 5 V / 3.3 V regulation, actuator power, the Dynamixel bus and safety control for AHPR Lotus. Designed in Altium Designer 26.

## Opening the project

Open `AHPR_Power_Management_and_Controls_Board.PrjPcb` in Altium Designer. Component libraries are in `Libraries/`: schematic symbols in `SchLib/`, footprints in `PcbLib/` and STEP models in `3D_Models/`. Every placed part except the H1-H4 mounting holes has a 3D model; the TLV75533PDBVR (U2, U13) and SN74LVC1G74DCUR (U7) footprints embed TI's STEP models (`3D_Models/TLV75533PDBVR.STEP`, `3D_Models/SN74LVC1G74DCUR.stp`).

## Board files

| File | Contents |
| --- | --- |
| `AHPR_Power_Management_and_Controls_Board.PcbDoc` | Routed board: placement, routing, ground pours, silkscreen. Part of the project. |
| `AHPR_Power_Management_and_Controls_Board_Unrouted.PcbDoc` | Same outline, placement, silkscreen, rules and ground pours with all tracks and vias removed. Not part of the project; open it directly. |

## Board summary

- 65 x 56 mm, 3 mm corner radius, 2 layers, ground pour on both sides
- Mounting holes H1-H4 at (3.5, 3.5), (61.5, 3.5), (3.5, 52.5), (61.5, 52.5) mm, matching the Pi
- J2 (2x20 header) on the bottom side, socket facing down onto the Pi; all other parts on top
- Camera ribbon slot 20 x 3 mm centred at (45, 11.5) mm

## Schematic sheets

1. Battery Input and Protection
2. 5 V and 3.3 V Regulation
3. Actuator Power and Dynamixel Bus
4. Safety Control
5. Pi Interface and IO

Requirements are in `AHPR Lotus Power Management PCB - Rev 2 BOM & Board Definition.pdf` and `AHPR Connector & GPIO Map.pdf`. `Rev1(drivers)/` holds the earlier Rev 1 driver schematics.

## Not yet done

- Antenna keep-out position is unverified (component-body clearance check is clean)
- No fabrication outputs (Gerbers, drill, pick-and-place) have been generated
