# FT232R-I2C-EEPROM

# OBJECTIVE 
Read and write data to an AT24C256 EEPROM using FT232R using a Logic Analyzer.

## Scope
This repository documents the read and write operations performed on an AT24C256 EEPROM using an FT232R interface, Python, a Logic Analyzer, and PulseView .

## What was done
1. Verified DTR clock generation.
2. Verified TX line pulsing using the 0x55 test pattern.
3. Verified I2C START condition generation.
4. Verified byte transmission.
5. Verified EEPROM write transaction.
6. Verified EEPROM read-back transaction.

## Hardware Used

FT232R USB-UART interface
AT24C256 I2C EEPROM
Logic Analyzer
Breadboard and jumper wires
4.7 kΩ pull-up resistors

## Hardware Connections

FT232R DTR → EEPROM SCL
FT232R TX → EEPROM SDA
FT232R RX → EEPROM SDA
FT232R VCC → EEPROM VCC
FT232R GND → EEPROM GND

## Additional connections:

SDA → 4.7 kΩ → VCC
SCL → 4.7 kΩ → VCC
A0, A1, A2 → GND
WP → GND

## Debugging Notes

During bring-up, the following issues were encountered and resolved:

- FT232R power collapse when connected to the EEPROM module.
- EEPROM moved from module PCB to breadboard testing.
- Verification of FT232R DTR polarity.
- Pull-up resistor placement verification.
- Logic Analyzer sampling adjustments.
- Validation of START condition timing.
- Verification of EEPROM write and read transaction flow.
## Conclusion

![Final read write waveform image ](Images/Read_Write_test_image.png)
An EEPROM write and read-back transaction was successfully implemented using FT232R control lines and Python. The generated I2C bus activity was captured and verified using a Logic Analyzer and PulseView, confirming that the value written to the EEPROM was successfully read back.
