# ModBus_RS485_Slave

Library for communicating with Modbus devices over RS232/USB/485 via RTU protocol

Ported to Particle by Paul Kourany, 2015

# Update May 2016

- Added in a RXEN pin
- Changed how RXEN and TXEN works

The SN65HVD70 is a RS485 device that should work identically to the MAX485.

RXEN and TXEN can be controlled independently by initializing like this: 
 Modbus master(0, 1, TXEN_PIN, RXEN_PIN); 

In configurations where the RS485 pins RXEN and TXEN are tied together, initialization changes to this:
 Modbus master(0, 1, TXEN_PIN); 

Otherwise, the operation is exactly the same. Both RS845 chips use serial communication and so will both need to conform to the same serial -> MODBUS communication pattern.
