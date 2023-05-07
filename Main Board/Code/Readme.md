# Arduino Files

Basic functional board setup:
  - 3 ATmega328/Arduinos interconnected through I2C.
  - Each Arduino has
    - 3 LEDs for discrete signals
      - Green LED - Digital Pin 3 (PD3)
      - Yellow LED - Digital Pin 5 (PD5)
      - Red LED - Digital Pin 6 (PD6)
    - 1 IR LED for interaction/driving the Lego Power function IR. - Digital Pin 10 (PB2)
      - [https://github.com/jurriaan/Arduino-PowerFunctions](https://github.com/jurriaan/Arduino-PowerFunctions)
    - Serial RX on Digital Pin 0 (PD0)
    - Serial TX on Digital Pin 1 (PD1)
    - I2C connectivity via standard SDA(PC4)/SCL(PC5) Pins

## Programming the Main board

Programming the main board utilizes the [Tiny AVR Programmer](https://www.sparkfun.com/products/11801) in conjunction with the [SparkFun ISP Pogo Adaptor](https://www.sparkfun.com/products/11591).

Setup to the Arduino IDE and when it is time to program the desired microcontroller ensure the following parameters are selected:

  - Board: Arduino Uno
  - Programmer: USBtinyISP

Then ensure the pogo adaptor is plugged in correctly to the Tiny AVR Programmer and seated firmly into the correct ISP Unit # on the Main Board. Then select Sketch->Upload Using Programmer 
