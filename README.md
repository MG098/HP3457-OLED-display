# HP3457-OLED-display
A modern replacement for the low contrast HP3457 Multimeter LCD

This is a remake of the original project made by Xyphro, remade in KiCad and with a simpler PCB.
It drops the complicated power supply structure and isolation, in favor of using internal charge pumps for OLED and a simple buffer chip.
The power is supplied directly through the ribbon cable.
Since the internal ribbon cable follows a DIP-16 dimensions, I decided to use a common DIP socket with pins bent flat to act as a SMD footprint.
This allows for a much simpler and smaller PCB, without the need to split it into two pieces, saving on cost and assembly.
I've also repladced the more uncommon ATMega8L with a very common ATMega328p.
The board is still fully compatibile with ATMega8L, however there are come changes in the code that needed to be made.
Below are the pictures for this simplified board:

<img src="https://github.com/MG098/HP3457-OLED-display/blob/main/photos/Display_Frontside.png?raw=true" width="80%"/>
<img src="https://github.com/MG098/HP3457-OLED-display/blob/main/photos/Display_Backside.png?raw=true" width="80%"/>

# The final result:

I've added a bit of acryllic glass to hide the space between the digits.

<img src="https://github.com/MG098/HP3457-OLED-display/blob/main/photos/annuciators_icons.png?raw=true" width="80%"/>

# Building the display yourself:

The build procedure is pretty much the same as the original project, but without splitting the board into two pieces.
It uses the same displays as the original project (SSD1316), and I haven't tested it with CH1115 displays.
The original Eagle files are left unchanged and server as a great inspiration.
My modified board is in KiCad folder, and I've also replaced the Gerber files.
If you decide to build this version, make sure that you use an ATMega that was programmed to use an internal oscillator.
I used one that I desoldered from an old arduino, and I couldn't program it before connecting external crystal.
Other fusebits should be set to 8MHz internal oscillator, with no divider.


# Putting it together

Since the display is now a single board, it's thinner than the original and won't fit easily into the multimeter.
For that, I've designed a simple bracket that enables the use of the original mounting holes.
I've included it the 3D folder, along with the 3D model for the board itself.
This bracked is 3D printed and uses brass threaded inserts and M3 screws.
It uses the original mounting holes and screws for the display itself.
After installing, the ribbon cable should fit nicely into the DIP socket and make electrical connection just fine.
The display is using the same 5V provided by the multimeter through the ribbon cable, so there is no need to hook it into AC supply section.
However, 5V into the display is connected through 1K resistor that would need to shorted, otherwise the voltage drop becomes too large.
Shown below is the resistor in question (R615), located right next to the ribbon cable connector.

<img src="https://github.com/MG098/HP3457-OLED-display/blob/main/photos/PowerConnection.png?raw=true" width="80%"/>


