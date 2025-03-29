# Gas Leakage Detector using GSM & Arduino with SMS Alert

## Overview
This project is designed to detect gas leakage using an MQ135 gas sensor and send an SMS alert using the SIM800 GSM module. The system displays the gas level on a 16×2 LCD display and triggers an SMS alert if the gas concentration exceeds a predefined threshold.

## Components Required
| S.N. | Component Name         | Quantity | Purchase Links |
|------|------------------------|----------|----------------|
| 1    | Arduino UNO Board      | 1        | [Amazon](#) | [AliExpress](#) |
| 2    | SIM800/900 GSM Module  | 1        | [Amazon](#) | [AliExpress](#) |
| 3    | 16x2 LCD Display       | 1        | [Amazon](#) | [AliExpress](#) |
| 4    | Potentiometer 10K      | 1        | [Amazon](#) | [AliExpress](#) |
| 5    | MQ2 Gas Sensor         | 1        | [Amazon](#) | [AliExpress](#) |
| 6    | 5V DC Supply           | 1        | [Amazon](#) | [AliExpress](#) |
| 7    | 12V DC Supply          | 1        | [Amazon](#) | [AliExpress](#) |
| 8    | Connecting Wires       | 20       | [Amazon](#) | [AliExpress](#) |
| 9    | Breadboard             | 1        | [Amazon](#) | [AliExpress](#) |

## How It Works
1. The MQ135 sensor continuously monitors the gas level.
2. The gas level is displayed on the LCD screen.
3. If the gas level exceeds the threshold, an SMS alert is sent to the specified mobile number.
4. The system updates every 2 seconds.

## Circuit Diagram
- Connect the MQ135 sensor's Analog pin (A0) to Arduino's A0.
- Connect the GSM module to an external 9V/12V power supply.
- The GSM module’s TX and RX pins are connected to Arduino's digital pins 9 and 10.
- The LCD display is connected to Arduino using digital pins 7, 6, 5, 4, 3, and 2.
- A 10K potentiometer is used to adjust the LCD contrast.

## Source Code
```cpp
#include <SoftwareSerial.h>
#include <LiquidCrystal.h>

SoftwareSerial sim800(9, 10); // RX, TX for GSM Module
LiquidCrystal lcd(7, 6, 5, 4, 3, 2);

const int gasSensor = A0;
const int threshold = 400; // Adjust this threshold based on testing

void setup() {
    pinMode(gasSensor, INPUT);
    lcd.begin(16, 2);
    lcd.print("Gas Detector");
    delay(2000);
    lcd.clear();
    Serial.begin(9600);
    sim800.begin(9600);
}

void sendSMS() {
    sim800.println("AT+CMGF=1"); // Set SMS mode to text
    delay(1000);
    sim800.println("AT+CMGS=\"+1234567890\""); // Replace with actual number
    delay(1000);
    sim800.println("Warning! Gas Leakage Detected!");
    delay(1000);
    sim800.write(26);
    delay(5000);
}

void loop() {
    int gasLevel = analogRead(gasSensor);
    lcd.setCursor(0, 0);
    lcd.print("Gas Level: ");
    lcd.print(gasLevel);
    
    if (gasLevel > threshold) {
        lcd.setCursor(0, 1);
        lcd.print("Leakage Detected!");
        sendSMS();
    } else {
        lcd.setCursor(0, 1);
        lcd.print("Safe          ");
    }
    
    delay(2000);
}
```

## Usage Instructions
1. Upload the above code to the Arduino UNO using the Arduino IDE.
2. Connect all the components as per the circuit diagram.
3. Insert a SIM card into the GSM module and power it on.
4. Monitor the LCD display and receive alerts via SMS in case of leakage.

## License
This project is open-source and free to use. Modify it as needed for your application.

