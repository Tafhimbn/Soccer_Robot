# Mobile controlled Soccer Robot / RC Car

![preview](https://user-images.githubusercontent.com/47665581/197787254-553773cc-87bd-45ce-855c-5b08c80bb14d.jpg)

## Parts and Tools Required

![image](https://user-images.githubusercontent.com/47665581/198278551-73ebeb69-30b5-49a0-b31b-95e63f17764b.png)

1. 4WD Robot Chassis kit
2. Arduino Uno
3. LM298 H bridge Module
4. Bluetooth Module HC-05
5. 12v Li-po Battery
6. Male-Female Jumper Wires
7. Male-Male Jumper Wires
8. Duct Tape or any other tape 9. Smartphone

## Structure / Chassis
You can buy Ready made 4WD Car chassis or you can make it by using PVC / Any kind of Hard Board .
![image](https://user-images.githubusercontent.com/47665581/198278445-5fb2d585-56ae-4827-bb30-7c9f5db01be8.png)


## Motor / Actuator

In this project i use 6v DC motor . You can used any kind of 6v DC motor .
![image](https://user-images.githubusercontent.com/47665581/198278422-67f173a4-fd83-463b-b332-f8a38ba0ca56.png)


## Mount the Motor and Install the Top Roof
![image](https://user-images.githubusercontent.com/47665581/198278216-95900a68-0ca1-4944-b768-bb8bb0f86a7b.png)
![image](https://user-images.githubusercontent.com/47665581/198278241-db871e31-a3b4-4bc9-91fa-70ecba062dce.png)
![image](https://user-images.githubusercontent.com/47665581/198278276-191cad1d-7f8d-444d-ad8d-bb02824bd94a.png)
![image](https://user-images.githubusercontent.com/47665581/198278299-8d6b9e0a-dad1-41ff-bd05-a61b00bcd682.png)


## Controller
![image](https://user-images.githubusercontent.com/47665581/198278158-b3f8c5fd-95df-4bb7-8a05-495999a2c14e.png)

The Arduino UNO is an open-source microcontroller board based on the Microchip ATmega328P microcontroller and developed by Arduino.cc.
The board is equipped with sets of digital and analog input/output (I/O) pins that may be interfaced to various expansion boards (shields) and other circuits. The board has 14 Digital pins, 6 Analog pins, and programmable with the Arduino IDE (Integrated Development Environment) via a type B USB cable. It can be powered by a USB cable or by an external 9 volt battery, though it accepts voltages between 7 and 20 volts. It is also similar to the Arduino Nano and Leonardo. The hardware reference design is distributed under a Creative Commons Attribution Share-Alike 2.5 license and is available on the Arduino website. Layout and production files for some versions of the hardware are also available. "Uno" means one in Italian and was chosen to mark the release of Arduino Software (IDE) 1.0. The Uno board and version 1.0 of Arduino Software (IDE) were the reference versions of Arduino, now evolved to newer releases. The Uno board is the first in a series of USB Arduino boards, and the reference model for the Arduino platform. The ATmega328 on the Arduino Uno comes preprogrammed with a bootloader that allows uploading new code to it without the use of an external hardware programmer.[3] It communicates using the original STK500 protocol. The Uno also differs from all preceding boards in that it does not use the FTDI USB-to-serial driver chip. Instead, it uses the Atmega16U2 (Atmega8U2 up to version R2) programmed as a USB-to-serial converter.

The microcontrollers are typically programmed using a dialect of features from the programming languages C and C++. In addition to using traditional compiler toolchains, the Arduino project provides an integrated development environment (IDE) based on the Processing language project.

## H Bridge ( LM 298 Module )
![image](https://user-images.githubusercontent.com/47665581/198278078-579d1be3-dcb9-4577-b2c8-53fb9101a5a0.png)

What is H- Bridge ?
The term H bridge is derived from the typical graphical representation of such a circuit .It is a circuit which can drive a DC motor in forward and reverse direction. Working : See the above picture for understanding the working of the H bridge.
![image](https://user-images.githubusercontent.com/47665581/198278122-8ffd52fc-cf1e-4b66-b89e-eba4cf8c66c8.png)

It is consists of 4 electronics switches S1,S2,S3 and S4 ( Transistors / MOSFETs/ IGBTS ). When the switches S1 and S4 are closed (and S2 and S3 are open) a positive voltage will be applied across the motor.So it rotates in the forward direction.Similarly when S2 and S3 are closed and S1 and S4 are opened a reverse voltage is applied across the motor, so rotates in revers direction.

Note : The switches in the same arm ( either S1,S2 or S3,S4) are never closed at a same time, it will make a dead short circuit. H bridges are available as integrated circuits, or you can built your own by using 4transistors or MOSFETs. In our case we are using LM298 H-bridge IC that can allows to control the speed and direction of the motors.

Pin Description :

Out 1: DC motor 1 "+" or stepper motor A+

Out 2: DC motor 1 "-" or stepper motor A-

Out 3: DC motor 2 "+" or stepper motor B+

Out 4: Motor B lead out

12v Pin :12V input but you can use 7 to 35V

GND: Ground

5v Pin: 5V output if 12V jumper in place, ideal for powering your Arduino (etc)

EnA: Enables PWM signal for Motor A (Please see the "Arduino Sketch Considerations" section)

IN1: Enable Motor A

IN2: Enable MotorA

IN3: Enable MotorB

IN4: Enable MotorB

EnB: Enables PWM signal for Motor B


## Power Source
Power Source
Those Battery can be used :

1. AA Alkaline Battery ( Non Rechargeable )
2. AA NiMh or NiCd Battery ( Rechargeable )
3. Li Ion Battery
4. LiPo Battery

## Electrical Wiring
For wiring you need some jumper wires.
Connect the red wires of two motors ( on each side )together and black wires together.
So finally you have two terminals in each side. MOTORA is in charge of two right side motors, correspondingly two left side motors are connected to MOTORB Follow the instruction below to connect everything.

### Motors Connection:

Out1 -> Left Side Motor Red Wire (+ )

Out2 -> Left Side Motor Black Wire ( - )

Out3 -> Right Side Motor Red Wire ( + )

Out4 -> Right Side Motor Black Wire ( - )

### LM298 - > Arduino

IN1 -> D5

IN2-> D6

IN2 ->D9

IN2-> D10

### Bluetooth Module -> Arduino

Rx-> Tx

Tx ->Rx

GND -> GND

Vcc -> 3.3V

### Power :

12V - > Connect Battery Red Wire

GND -> Connect Battery Black wire and Arduino GND pin

5V -> Connect to Arduino 5V pin

### Control Logic

![image](https://user-images.githubusercontent.com/47665581/198277998-4fe13bb9-b9ca-4a1c-8f85-5a2dba63ad96.png)


### Software

![image](https://user-images.githubusercontent.com/47665581/198277943-e937ff05-ae90-44d1-9142-6fa86ec9d63c.png)
![image](https://user-images.githubusercontent.com/47665581/198277965-7dea6954-fa3c-4a0b-9cb0-2ec1be1c2aaf.png)

The software part is very simple,it does not need any library.If you understand the logic table in the earlier steps then you can write you own code. I didn't spend much time on writing the code, so just using a code written by someone else.To control the Robot Car, I am using my smartphone.The smartphone is connected to the controller via a Bluetooth module ( HC -06 /05) Download the App After installing the app, you have to pair it with the Bluetooth module.The password for pairing is " 1234 ".

APP link: https://play.google.com/store/apps/details?id=braulio.calle.bluetoothRCcontroller

# Tutorial: 
https://www.youtube.com/watch?v=cC2crT941wQ&list=PLSB-TihimdqBUxWu_m5Xej-MXkZ_9iMoC
