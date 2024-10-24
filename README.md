# Arduino RFID Card Validation with LEDs, Buzzer, and Potentiometer

![Screenshot 2024-10-24 at 8 44 27 PM](https://github.com/user-attachments/assets/b02c4395-5a6e-461e-9439-5be7e8a43047)

This project demonstrates how to create a system that validates a specific RFID card using an Arduino Uno, MFRC522 RFID module, LEDs (red and green), an active buzzer, and a potentiometer. The system lights a green LED if the card is valid and lights a red LED while sounding the buzzer repeatedly for 3 seconds if the card is invalid. The potentiometer is used to control the buzzer's volume.

## Components Used:
- Arduino Uno R3 (1x)
- MFRC522 RFID Reader (1x)
- Active Buzzer (1x)
- Green LED (1x)
- Red LED (1x)
- Potentiometer (10kΩ) (1x)
- Breadboard (1x)
- Jumper Wires (27x)
- 220Ω Resistors for LEDs (2x)

## Circuit Diagram:

1. **RFID MFRC522 Connections**:
   - `VCC`: Connect to 3.3V on the Arduino.
   - `GND`: Connect to GND on the Arduino.
   - `SDA`: Connect to Pin 10 on the Arduino.
   - `SCK`: Connect to Pin 13 on the Arduino.
   - `MOSI`: Connect to Pin 11 on the Arduino.
   - `MISO`: Connect to Pin 12 on the Arduino.
   - `RST`: Connect to Pin 9 on the Arduino.

2. **LED Connections**:
   - **Green LED**: 
     - Connect the `Anode (+)` to Pin 7 on the Arduino via a 220Ω resistor.
     - Connect the `Cathode (-)` to the ground (GND) rail on the breadboard.
   - **Red LED**: 
     - Connect the `Anode (+)` to Pin 6 on the Arduino via a 220Ω resistor.
     - Connect the `Cathode (-)` to the ground (GND) rail on the breadboard.

3. **Buzzer Connections**:
   - Connect the positive leg (`+`) of the active buzzer to the wiper (middle pin) of the potentiometer.
   - Connect the negative leg (`-`) of the buzzer to the ground (GND) rail on the breadboard.

4. **Potentiometer Connections**:
   - Pin 1 (left terminal) connects to 5V on the Arduino.
   - Pin 3 (right terminal) connects to the ground (GND) rail on the breadboard.
   - Pin 2 (middle terminal) connects to the positive pin of the buzzer.

## Wiring Configuration:

- Place all components (RFID module, LEDs, buzzer, potentiometer) on a breadboard to make wiring easier and cleaner.
- Ensure that the breadboard's ground (GND) rail is connected to the Arduino's ground.
- Use the breadboard's 5V and GND lines for easy access to power for your components.
  
### Steps:
1. Connect the RFID module to the Arduino according to the wiring configuration.
2. Set up the LEDs on the breadboard, making sure each one is connected to its respective Arduino pin and GND.
3. Connect the active buzzer to the potentiometer as described, and wire the potentiometer to control the buzzer's volume.
4. Ensure all connections are correct by following the pin layout described above.

## Setup Instructions:
1. **Install Libraries**:
   - In the Arduino IDE, go to **Sketch > Include Library > Manage Libraries**.
   - Search for `MFRC522` and install the **MFRC522** library.

2. **Upload Code**:
   - Open the Arduino IDE.
   - Paste the provided code (you can find this in the project files).
   - Select your board as **Arduino Uno** from **Tools > Board** and choose the correct port from **Tools > Port**.
   - Click **Upload** to load the code onto your Arduino.

3. **Test the System**:
   - Open the Serial Monitor in the Arduino IDE to view the RFID card's UID and see the validation results.
   - Use the potentiometer to adjust the buzzer's volume based on your preference.

## How It Works:
- When an RFID card is scanned, the system reads its UID.
- If the scanned card matches the pre-configured valid UID:
  - The **Green LED** will light up.
  - The **Buzzer** will beep once to indicate success.
- If the scanned card does not match:
  - The **Red LED** will light up.
  - The **Buzzer** will sound repeatedly for 3 seconds to indicate failure.
  - The volume of the buzzer can be controlled using the **Potentiometer**.

## Troubleshooting:
- Ensure that the RFID module is correctly wired to the SPI pins (MOSI, MISO, SCK).
- Make sure the LEDs and the buzzer are connected to the correct Arduino pins.
- Check for loose connections on the breadboard, especially for power (5V) and ground (GND).

## License:
This project is released into the public domain.
