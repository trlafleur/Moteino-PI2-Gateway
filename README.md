# Moteino-PI2-Gateway
This PCB will interface a Moteino or a RFM69H(W) radio to a Raspberry PI2

Raspberry PI2 Gateway board.

This board will connect to a Raspberry PI2 (and maybe a B+) and provide an interface to the LowPower or MySensor network.

The board is approximately 2.1 x 2.75in, in size and has three basic options.

1)	It will connect a Moteino via its serial port to the Raspberry PI2 serial port.

2)	Or it will connect a Moteino Mega via its serial port to the Raspberry PI2 serial port.

3)	Or it will connect a HopeRF, RFM69W(H) radio directly to the Raspberry PI2 SPI I/O lines.

The Moteino’s serial port 0, is connected to the Raspberry PI2 internal serial port: /dev/ttyAMA0 on I/O pins: GPIO-14, TX pin 8 and GPIO-15, RX pin 10. 

Programing of the Moteino’s can be done directly via the Raspberry PI2 or via the standard programming header on the Moteino’ s. If using the Moteion’s standard serial port connector for programming, a jumper, P2 on the board need’s to be removed when programming to avoid conflict in serial I/O lines with the PI and re connected for normal use.

The group at: http://openenergymonitor.org/emon/ has developed a guide on how to program the Moteino (ATmega328) directly from the Raspberry PI. They have also developed a small RFM69Pi adapter board that contain a RFM69 radio and a ATmega328. (Somewhat equivalent to this board and a Moteino)

http://wiki.openenergymonitor.org/index.php/RFM69Pi_V3

This board also allows direct connection of a RFM69W(H) radio to the Raspberry PI via I/O pins. It provide a u.LF connector for an external antenna or a wire antenna. Connection to the PI are made via the PI’s SPI interface.

Some examples on how to use this option are given below.

http://rdepablos.merlitec.com/mixed/rfm69-library-for-raspberry-pi

https://github.com/etrombly/RFM69

https://github.com/abouillot/HomeAutomation/tree/master/piGateway

Full schematics and Gerber’s are available here.

There are 4 optional LED’s on the board that can be used by your software as needed. See schematic for connected pins to the Moteino’s. Also there is an option for a zero ohm resistor that will allow you to reset the Moteino’s via the PI.

For the RFM69W(H) radio, all pins are connected via resistor of 0 to about 47 ohm (not critical) to provide some isolation from the PI’s SPI lines. These also provide a good test point for monitoring the I/O lines during development. Per the RFM69W(H)  data sheet, the board also provide a place for a 10uf or larger capacitor and a .1uf capacitor near the radio.

All parts on the board are 0805 size components that are easy to solder.

Errata:

1) cathode end of LED's are marked wrong on silk-screen

2) Warrning: On my Moteino's, prior to development of this board, I had cut the pin that supplies 3.3V from the FTDI connector. Not doing so, will cause the power from the FTDI and the PI2 to be in competition. I suggest you cut the pin or make an adapter removing the 3.3v pin.



