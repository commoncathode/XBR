# XBR
The XBR is a cross-band repeater controller, intended for use with amateur radio transceivers. The radio ports are designed to work with the Yaesu FT-891 and Motorola XTL5000, but the circuitry is generic enough that, with some adjustment, it may very well work with a variety of radio transceivers. The heart of the controller is a Freescale/NXP 8-bit microcontroller, the MC9S08SH8.

**Background**

The main idea for this interface arose from the public service aspect of amateur (or "ham") radio. My club did a lot of public service events before the pandemic, such as foot and bike races. One event we were requested to assist with had a race course that covered much of the state, and so the differing terrain would make it difficult to maintain radio contact with the club's VHF repeater system. To fill in the weak spots, we thought "well, what about low band VHF, or even HF?" And I started to think, "better yet, what if all stations could hear one another, even if they were operating on a different band?" Thus, this interface is designed to link an HF/50 MHz radio to a VHF radio, in order to cross-link a VHF repeater onto an HF simplex frequency. Ideally, 28 or 50 MHz FM simplex linked to a 144 or 440 MHz repeater or repeater system.

**Operation**

Version 1 of the interface (or controller) is extremely simple in operation, designed to simply pass radio traffic automatically between two transcievers. It is not capable of linking repeaters or connecting to AllStar/Echolink. There is an impolite ID function that transmits on both radios every 10 minutes, non-adjustable. The tail is 500mS, non-adjustable. The ID function may be suitable for most users, but please follow your local governance for amateur radio operation. As I am in the US, the controller includes an active-low contact for disabling the repeater remotely to comply with FCC Part 97 regulations.

**Revisions**

A few features I hope to add in the future are as follows.
- Capability to adjust all parameters over a serial terminal, such as:
- Call sign
- Tail length
- Polite ID function
- ID inactivity timer
- ID speed and pitch adjustment in words per minute (beta)
- Timeout timer length
- Enable/disable repeater over serial
- PTT and COR logic (active hi/lo)

**Errors**

1) With the components installed as outlined in the BoM, the ID function does not correctly pass audio to the mic inputs. You get sort of a "thumping" instead of a sine wave at 440Hz. This may be due to a low output impedance of the transformer coupled with the 10k resistors on the output; I am in the process of testing and verifying a few different solutions. 
2) The ID transformer's input is not referenced to common. I suggest scratching off some soldermask on the bottom next to the pad and bridging one side to the GND pour.
3) Impedance mismatch on the VHF port's mic circuit - just decoupled DC with a 4.7uF cap and jumped input to output in place of transformer TR2. This was an oddity with the radio I was using, so YMMV. 
Please view the schematic file or PDF print for a complete list of errata. 
