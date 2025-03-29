# Gas_detection_system
Gas Leakage Detector using GSM & Arduino with SMS Alert
In this project, we are going to learn how to design a Gas Leakage Detector using GSM & Arduino with SMS Alert. We will interface Sim800 GSM Module as well as MQ135 Gas Sensor with Arduino. The gas level value will be displayed on the 16×2 LCD Display. Whenever the excess gas is detected SMS will be sent to a particular phone number.





Smoke and gas leakage detectors are very useful in detecting smoke or fire in buildings, and so are the important safety parameters in order to prevent disasters. Bursting cylinders and accidental fires have caused lots of harm to the economies in the past. This circuit triggers the alert system when smoke or gas leakage is detected. The circuit mainly uses the MQ135 Smoke/Gas sensor and Arduino to detect and smoke and gas leak. This MQ135 gas sensor is sensible to LPG, Alcohol, and Methane etc.It detects the presence of a dangerous LPG leak in your car or in a service station, storage tank environment. The sensor has excellent sensitivity combined with the quick response time. The sensor can also sense iso-butane, propane, LNG, and cigarette smoke. If the LPG sensor senses any gas leakage from storage the output of this sensor goes low. This low signal is monitored by the microcontroller and sends the signal to GSM module to send messages as “Gas Leakage” to a mobile number written in code.

You can also use SIM900 or any other GSM Module instead of SIM800. Similarly you can use MQ2/MQ3/MQ5 or any other Gas/Smoke Sensor instead of MQ135.

To learn more about the gas sensors you can follow these post:

Alcohol Level Meter using Arduino & MQ-135 Alcohol/Gas Sensor
Arduino Smoke Level Detector using MQ-135 Sensor with Alert Alarm
Gas Leak Alarm System using MQ2 & Arduino
Bill of Materials
S.N.	Components Name	Quantity	Purchase Links
1	Arduino UNO Board	1	Amazon | AliExpress
2	SIM800/900 GSM Module	1	Amazon | AliExpress
3	16x2 LCD Display	1	Amazon | AliExpress
4	Potentiometer 10K	1	Amazon | AliExpress
5	MQ2 Gas Sensor	1	Amazon | AliExpress
6	5V DC Supply	1	Amazon | AliExpress
7	12V DC Supply	1	Amazon | AliExpress
8	Connecting Wires	20	Amazon | AliExpress
9	Breadboard	1	Amazon | AliExpress





SIM800 GSM Module
Description
SIM800 is a quad-band GSM/GPRS module designed for the global market. It works on frequencies GSM 850MHz, EGSM 900MHz, DCS 1800MHz, and PCS 1900MHz. SIM800 features GPRS multi-slot class 12/ class 10 (optional) and supports the GPRS coding schemes CS-1, CS-2, CS-3 and CS-4. With a tiny configuration of 24243mm, SIM800 can meet almost all the space requirements in users’ applications, such as M2M, smartphone, PDA and other mobile devices.

Sim800 GSM Module

SIM800 has 68 SMT pads and provides all hardware interfaces between the module and customers’ boards. SIM800 is designed with power-saving technique so that the current consumption is as low as 1.2mA in sleep mode. SIM800 integrates TCP/IP protocol and extended TCP/IP AT commands which are very useful for data transfer applications.

Features
• Support up to 552 Keypads.
• One full function UART port, and can be configured to two independent serial ports.
• One USB port can be used as debugging and firmware upgrading.
• Audio channels which include a microphone input and a receiver output.
• Programmable general-purpose input and output.
• One SIM card interface.
• Support Bluetooth function.
• Support one PWM.
• PCM/SPI/SD card interface, only one function can be accessed synchronously.
• Power supply 3.4V ~ 4.4V
• Typical power consumption in sleep mode is 1.2mA
• Frequency bands GPRS multi-slot class 12
• Support SIM card: 1.8V, 3V
• Serial Port: Can be used for AT commands for data stream
• USB Port: Can be used as debugging and firmware upgrading





MQ135 Gas/Smoke Sensor
Description
The MQ-135 gas sensor senses the gases like ammonia nitrogen, oxygen, alcohols, aromatic compounds, sulfide, and smoke. The MQ-3 gas sensor has a lower conductivity to clean the air as a gas sensing material. In the atmosphere we can find polluting gases, but the conductivity of gas sensor increases as the concentration of polluting gas increases. MQ-135 gas sensor can be implemented to detect the smoke, benzene, steam and other harmful gases. It has the potential to detect different harmful gases. It is with low cost and particularly suitable for Air quality monitoring applications.

Gas Leakage Detector using GSM & Arduino with SMS Alert

The MQ135 sensor is a signal output indicator instruction. It has two outputs: analog output and TTL output. The TTL output is low signal light which can be accessed through the IO ports on the Microcontroller. The analog output is a concentration, i.e. increasing voltage is directly proportional to increasing concentration. This sensor has a long life and reliable stability as well. Check the MQ135 Datasheet to learn more.

Features
• High Sensitivity
• High sensitivity to Ammonia, Sulfide, and Benze
• Stable and Long Life
• Detection Range: 10 – 300 ppm NH3, 10 – 1000 ppm Benzene, 10 – 300 Alcohol
• Heater Voltage: 5.0V
• Dimensions: 18mm Diameter, 17mm High excluding pins, Pins – 6mm High
• Long life and low cost

Circuit: Gas Leakage Detector using GSM & Arduino with SMS Alert
So here is a circuit for Gas Leakage Detector using GSM & Arduino with SMS Alert. Assemble the circuit as shown in the figure below.

Gas Leakage Detector using GSM & Arduino with SMS Alert

Supply MQ135 Sensor with 5V Power Supply. Connect its Analog pin A0 to Analog pin A0 of Arduino.

Similarly, Connect the GSM Module with 9V/12V external Power Supply. Only the Tx, Rx and GND pin of Sim800 Modem is connected to Arduino. So connect Tx & Rx to Pin No. 9 & 10 of Arduino respectively.

Connect the LCD to pin no 7,6,5,4,3,2 of Arduino. Supply it with 5V Power Supply. Use a 10K POT to adjust the contrast.

Source Code/Programs:
Here is a Source Code or Program for Gas Leakage Detector with SMS Alert using GSM Module & Arduino. Copy this code and upload it to Arduino Board using Arduino IDE.


