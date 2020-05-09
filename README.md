# STM32F4_SPI_2Boards

1. Description

A STM32F4 Discovery board acting as master, sends by SPI aa adress command to another board acting like slave. The second board reads ADC1 IN1 and sends back the conversion result in 4 digit +LF format, by SPI to the master board.
The achisition speed is fixed by master (limited by USART) and a led is toggling on slave at each request.
Master sends this string by UART1 115200/n/8/1 to a LabView application, which displays it. 

2. How to use

Dowload the whole content of the project.
For master, run the CubeMX file SAIP10m.ioc and generate project for IAR EWARM. Open the generated project, Download and Degug (Ctrl+R) in the Master board, then Go (F5).
For master, run the CubeMX file SAIP10s.ioc and generate project for IAR EWARM. Open the generated project, Download and Degug (Ctrl+R) in the Slave board, then Go (F5).
In the Live watch field of the board we may see the Tx and Rx buffers as in the file Screen1.png.
When the attached Labview file (LV1_4zecimal.vi) is run with the proper COM port, we may see the chart of the IN1 signal as in file Screen2.png.  

3. Software context

The project was verified using:

-STM32 Cube MX version 5.6.0

-Firmware package STM32Cube FW_F4 V1.25.0

-IAR-EWARM v 8.50.1.

-LabView 16.0(32 bits)

Notice: For other software context, some modifications may be necessary, as the future evolution of these products is unknown.

4. Hardware context

-STM32F4 -Discovery, as Master with USART1 on PB6 and PB&, and SPI on PB3, PB4 and PB5.

-STM32F4 -Discovery, as Slave with with SPI on PB3, PB4 and PB5 and a potentiometer on PA1, GND and VCC.

-GND of the two boards must be connected also.

-CH340  TTL to USB adapter on Master

5. Youtube classroom: https://www.youtube.com/watch?v=iAtq2m6YlyU&t=544s
