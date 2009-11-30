README for TestPromiscuous
Author/Contact: tinyos-help@millennium.berkeley.edu

Description:

In this application the node enables promiscuous mode, i.e. its radio is
switched to receive mode and all incoming frames that pass the CRC check are
signalled to the upper layer. The application uses the TinyOS printf library
(tos/lib/printf) to output information on the MAC header fields and payload for
every received frame over the serial port. The second (TelosB: green) LED is
toggled whenever a frame is received.

Criteria for a successful test:

A successful test means that for every received frame the second LED is toggled
and the java application outputs some text. To see this effect you need a
second node sending a packet. The TestPromiscuous application does not send
packets, but you can, for example, use the
../../beacon-enabled/TestStartSync/coordinator application to send periodic
beacon packets. In this case you should see some new text and the second LED
should toggle every half second.


Tools: The printf java client in $TOSDIR/../apps/tests/TestPrintf

Usage: 

Install the application on a node

    $ make <platform> install

Start the printf client, e.g. 

    $ java net.tinyos.tools.PrintfClient -comm serial@/dev/ttyUSBXXX:<platform>

(http://docs.tinyos.net/ has a section on how to use the TinyOS printf library)

Known bugs/limitations:

- The timestamps for ACKs are incorrect

$Id: README.txt,v 1.1 2009-10-29 17:42:56 janhauer Exp $
