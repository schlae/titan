# Titan Technologies Accelerator PC

There's very little information available about this 1984 accelerator card designed for the IBM PC and IBM XT, but here's what I was able to cobble together from a card and a little reverse engineering work.

Specifications
- Designed to upgrade the IBM 5150 PC or the IBM 5160 XT
- Onboard Intel 8086 running at 9.54MHz. (Twice the usual 4.77MHz clock)
- Optional memory daughterboard supporting up to 640KB of RAM with a 16-bit data path: twice the memory bandwidth as the 8088.

There is a row of jumpers running along the top of the card:
- P: Close to enable parity on the RAM daughtercard
- 0, 1, 2, 3, 4: Close to enable this bank of RAM on the daughtercard
- F, S (3 each): Set three jumpers to F for fast RAM (200ns or faster), S for slow RAM (250ns or slower). All three must have the same setting. The numbers are guesses based on logic analyzer measurements.

The daughtercard supports up to 640KB of RAM in 5 banks of 128KB each. The chips are 4164 devices. Each bank has two associated parity chips (optional) located in the narrow part of the daughtercard. For the PC to detect the RAM, be sure the switch bank SW2 is set correctly on the motherboard.

The accelerator card uses a ribbon cable with an IDC-to-DIP adapter crimped at the end, designed to plug into the CPU socket on the motherboard. The connector on the accelerator card has a pin 1 mark, but it is wrong: pin 1 is located at the end of the connector nearest the bracket. This corresponds with pin 1 and pin 40 of the 8088 CPU IDC plug.

Above the 8086 CPU on the accelerator card is a socket for the optional 8087. If you plan to use one, make sure it is rated for 10MHz.

If you need to repair the card, take a look at the reverse engineered schematic.

[Schematic](https://github.com/schlae/titan/blob/main/titan.pdf)

Included in this repository are the ROM and PAL images, just in case yours have gone bad.

