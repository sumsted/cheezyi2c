Cheezy I2C
===============

Makeblock mBot project, Arduino using C++

This is a copy of roboplayground. Need as rp is getting too big and can't fit in these mbots. Ripped out serial bt and commented out code in commands. IR button 8 triggers slave to send ultrasonic sensor value.

I2C Arduino communication payload format below. Payload length may be set at compile time. First byte is command to be executed by slave. Command could be a request to move a motor or to provide data from a sensor. The second byte indicates the type of data to be shared, either int (long) or bytes. Ints are translated to network byte order when placed in payload. The padding bytes may be populated by and used to indicate source of requested data, like slave #1.

        00  Command
         1  Value Type
         2  Padding
         3  Padding
         4  byte value   int[0] long
         5  byte value   int[0] long
         6  byte value   int[0] long
         7  byte value   int[0] long
         8  byte value   int[1] long
         9  byte value   int[1] long
        10  byte value   int[1] long
         1  byte value   int[1] long
         2  byte value   int[2] long
         3  byte value   int[2] long
         4  byte value   int[2] long
         5  byte value   int[2] long
         .
         .
         .
        32  byte value   int[4] long

