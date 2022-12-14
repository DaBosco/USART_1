# USART_1
This program is developed to give a basic example about USART serial communication. 
The first board (the master, NUCLEO-L496ZG board) transmits datas which are received by the second one (the slave, NUCLEO-U575ZI board). 
To permit the observer to understand if everything is right during the communication, we use built-in leds of the 2 boards.

Note: Hel_Delay for debouncing, not optimized.

--- MASTER SETUP: Transmitter. NUCLEO-L496ZG board. 

USART1
-PA9: TX
-Baud Rate 115200 Bits/s
-Word Lenght 8 Bits (parity bit: None)
-Transmit Only

Button
-Blue button: PC13

Led
-LD1: PC7

HCLK
-16 MHz

---------

___How it works:
Click Blue button
I2C communication starts, sending this set of data: 1,2,3,4,5,6,7,8,9
LD1 turn on
Leave blue button: stop transmitting 


--- SLAVE SETUP: Receiver. NUCLEO-U575ZI board.

USART1
-PA9: TX
-Baud Rate 115200 Bits/s
-Word Lenght 8 Bits (parity bit: None)
-Receive Only

Led
-LD1: PC7

HCLK
-16 MHz

___How it works:
The datas are read and compared.
If they are read correct (1,2,3,4,5,6,7,8,9 is the arrival buffer), slave's LED1 turn on.
