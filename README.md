# openAFMCircuits

This is the repo for the circuit schematics and layouts for the openAFM board.

There are 4 boards that control the openAFM hardware.  These are

1. Main Board
2. Piezo Board
3. Voice Coil Board
4. Input Board

A brief descripion of each board is given below.  For more details look in the folder for each board.  Each board has a pair of 10-pin headers on either side.  These have a female connector on the top, and long lines that extend through the board and produte from the bottom.  These interboard headers allow the boards to stack on top of eachother, whilst sharing 20 common pins.

# Main Board

This board takes in 12V DC from the power supply.  It is responsible for regulating this down to 5V, and distributing power (12V, 5V and GND) to the other boards via the interboard headers.  It is responsible for generating a constant current for the laser diode in the DVD head, and routing signals from other boards (via the interboard headers) to the DVD head.  The DVD head connects directly to this board via a ribbon cable.  The board takes signals from the arduino (via the 10-pin female header) and routes them to the appropriate pins on the interboard headers to be shared with the other boards.

# Input Board

This board deals with the inputs from the 4 photodiode quadrants on the DVD head (labelled as A, B, C and D).  It routes these directly to an ADC, calculates differences and summs in hardware and routes these to another ADC.

# Piezo Board

This board has a 4 channel DAC which is used to control the signals to move each of the 4 piezo quadrants that control the stage movement.  It takes the 4 voltages from the DAC and amplifies them to give a larger range.

# Voice Coil Board

Has a DAC that, along with a pair of push-pull amplifiers, generates the required current to drive the voice coils in the DVD head (focus and tracking).
