# -Design-and-Development-of-an-ESP32-P4-Based-IoT-Energy-Monitoring-Gateway-PCB
   Design and Development of an ESP32-P4 Based IoT Energy Monitoring Gateway PCB with Ethernet and Wi-Fi Connectivity
   Design and Development of an ESP32-P4 Based IoT Energy Monitoring Gateway PCB with Ethernet and Wi-Fi Connectivity

Project Overview
This project focuses on the design and development of an ESP32-P4-based IoT Energy Monitoring Gateway PCB for monitoring electrical energy parameters and enabling remote data communication. The system interfaces with an energy meter to obtain electrical consumption information, while the PZEM-004T energy measuring module measures parameters such as voltage, current, power, and energy consumption from the AC supply.
The ESP32-P4 microcontroller processes the collected data and enables data communication through Ethernet and Wi-Fi. A MAX485CSA transceiver supports RS-485 communication with the energy meter, while a TXS0102DCUR level shifter provides voltage-level compatibility between interfacing circuits. An OLED display provides local monitoring, and an RGB LED indicates system status.
The PCB integrates an AC-DC converter and buck converters to generate the required DC supply voltages for the circuit components. The proposed system provides a compact platform for energy data acquisition, local display, and network-based monitoring, with potential applications in smart energy management and industrial monitoring systems.


<img width="539" height="372" alt="Screenshot 2026-10-10 135713" src="https://github.com/user-attachments/assets/c4bd391f-daa9-4486-8c00-d80049581c8f" />



Power Input
1. AC Screw Terminal (230 V AC)
- Provides a secure connection for the 230 V AC input supply.
- Ensures reliable power input for the AC section.

2. DC Jack (12 V DC)
- Provides a convenient connection for the 12 V DC input supply.
 Supplies power to the low-voltage DC circuits through the power regulation stage.

AC POWER PROTECTION CIRCUIT:

A fuse protects the circuit against excessive current flow. When the current exceeds its rated limit, the fuse melts and disconnects the power supply. This helps prevent component damage and reduces the risk of overheating and fire.
An MOV protects the circuit against sudden voltage surges in the AC supply. Under normal voltage, it has high resistance. During a voltage surge, its resistance decreases, allowing it to divert surge current and limit the voltage reaching the protected circuit. This helps protect sensitive components from transient overvoltage.






PZEM-004T V3.0 Energy Measurement Module

The PZEM-004T V3.0 measures AC voltage, current, active power, energy consumption, frequency, and power factor. The AC input is connected to the module for voltage measurement.
Current Transformer (CT) measures the load current. The module communicates with the ESP32-P4 through UART serial communication


Three-Phase Energy Meter with RS485 Communication

A three-phase, four-wire energy meter is used to measure electrical energy consumption in three-phase systems. It monitors parameters such as voltage, current, power, and energy consumption across the three phases. 
Compared to the PZEM-004T V3.0, which is generally used for single-phase measurements, this meter is suitable for industrial three-phase energy monitoring. When equipped with RS485 communication, it can transmit measurement data to the ESP32-P4 through an RS485 transceiver. This enables centralized monitoring, reliable long-distance communication, and integration with an IoT-based energy monitoring system.

Voltage Level Shifter (TXS0102DCUR)

The TXS0102DCUR is used to interface the 5 V UART signals from the PZEM-004T V3 with the 3.3 V logic signals of the ESP32-P4. It provides bidirectional voltage-level translation between the two devices, helping ensure compatible UART communication and protecting the ESP32 from incompatible logic levels.

HLK-10M05 AC-DC Power Module

The HLK-10M05 is an AC-to-DC power module used to convert 230 V AC input into a regulated 5 V DC output. It supplies power to the low-voltage components in our energy monitoring gateway PCB. It provides an isolated power supply, helping separate the high-voltage AC input from the low-voltage circuit.

DC-DC Buck Converter Power Supply

The power supply section uses buck converters to step down the input voltage to the required levels for different components in the energy monitoring gateway PCB. The 12 V DC input from the DC jack is converted to 5 V, then 5 V is stepped down to 3.3 V, and finally 3.3 V is converted to 1.1 V for the corresponding circuit requirements. This provides the required voltage levels for the ESP32 and other components.

Voltage conversion: 12 V DC → 5 V → 3.3 V → 1.1 V.

Ethernet and Wi-Fi Connectivity

Ethernet: Provides a stable, wired network connection for reliable energy data transmission and remote monitoring.
Wi-Fi: Enables wireless connectivity for transmitting energy monitoring data to a dashboard or IoT platform.
Output Devices
OLED Display: Displays energy monitoring parameters and system status using I²C communication with the ESP32-P4.
RGB LED: Indicates different system operating conditions through colour changes, providing visual status alerts.

Wi-Fi Antenna Keep-Out Zone
A keep-out zone is maintained around the ESP-12F Wi-Fi antenna without copper traces, ground planes, or components. This prevents electromagnetic interference and signal obstruction near the antenna. It helps improve RF signal strength, wireless communication reliability, and overall Wi-Fi performance.

AC and DC Section Separation

AC Section: Contains the 230 V AC input and related protection components. It is separated to reduce electrical interference and improve safety.
DC Section: Contains low-voltage circuits such as the ESP32-P4, OLED and communication interfaces. It supports stable operation and reduces noise coupling from the AC section.

3D MODEL














VOLTAGE AND CURRENT RATING:

S.No.
Component Name
Maximum Voltage
Maximum Current
1
PJ-102A DC Jack
24 V DC
2.5 A
2
ESD Protection Diode
12 V Working / 15.5 V Clamping
1 A Peak Pulse
3
Buck Converter (5 V to 3.3 V)
17 V Max Input
3 A
4
Buck Converter (12 V to 5 V)
28 V Max Input
2 A
5
Buck Converter (3.3V to 1.1V)
5.5 V DC 
2 A 
6
Fuse
250 V AC/DC
6.3 A
7
MOV
275 V AC / 350 V DC
1200 A Surge
8
HLK-10M05 AC-DC Converter
264 V AC Input / 5 V DC Output
2 A
9
MAX485CSA RS-485 Transceiver 
5.5 V DC 
2 A 
10
TXS0102 Voltage Level Shifter
A-side: 3.6 V / B-side: 5.5 V
±50 mA Absolute Maximum
11
ESP32-P4NRW32
3.3 V DC


12
ESP-12F Wi-Fi Module
3.6 V DC Max
300 mA Peak
13
OLED Display DM-OLED096-636
3.3 V DC
12 mA                                                          
14
RGB LED 
2.1 V Red / 3.1 V Green & Blue (max forward voltage) 
2 mA 
15
WIZ850io Ethernet Module
3.3 V DC
43 mA








DATA SHEET

1.esp32-p4nrw32:
https://www.snapeda.com/parts/ESP32-P4NRW32/Espressif%20Systems/datasheet/

2.DC Jack:
https://www.snapeda.com/parts/PJ-102A/Same%20Sky/datasheet/

3.ESD:
https://www.snapeda.com/parts/ESD12VD3B-TP/MCC/datasheet/

4.FUSE:
https://www.snapeda.com/parts/FX0321/Bulgin/datasheet/

5.HLK:
https://www.lcsc.com/datasheet/lcsc_datasheet_2409141603_HI-LINK-HLK-10M05_C403745.pdf

6.VOLTAGE SHIFTER: https://www.alldatasheet.com/datasheet-pdf/view/173715/TI/TXS0102DCUR.html
7.PZEM-004T:
https://innovatorsguru.com/wp-content/uploads/2019/06/PZEM-004T-V3.0-Datasheet-User-Manual.pdf

8. 5V BUCK COVERTOR:
https://www.alldatasheet.com/datasheet-pdf/view/1009587/TI1/TPS259541DSGR.html

10. 3.3V BUCK CONVERTOR:
https://www.alldatasheet.com/datasheet-pdf/view/546290/TI1/TPS62130RGTR.html

10.1.1V BUCK CONVERTOR:
https://www.alldatasheet.com/datasheet-pdf/view/881531/TI1/TLV62569DBVR.html

11.WIFI MODULE:
https://www.quick-teck.co.uk/Management/EEUploadFile/1548298650.pdf

12.OLED DISPLAY:
https://universal-solder.ca/downloads/canaduino_oled_1.3_i2c.pdf

13.ETHERNET PORT:
https://www.snapeda.com/parts/WIZ850IO/WIZnet/datasheet/

SCHEMATIC:

<img width="609" height="404" alt="Screenshot 2026-10-10 140537" src="https://github.com/user-attachments/assets/515af454-e37f-4d56-94b4-3f402e81737e" />
<img width="555" height="367" alt="image" src="https://github.com/user-attachments/assets/17d448f9-99f9-4f0f-aab1-14229c142d43" />
<img width="556" height="367" alt="image" src="https://github.com/user-attachments/assets/16b0cbac-19b4-4df4-b4b2-9a29cc2d497f" />
<img width="555" height="367" alt="image" src="https://github.com/user-attachments/assets/de70a583-85b0-487c-a200-f3c2255ab77c" />
<img width="503" height="332" alt="image" src="https://github.com/user-attachments/assets/1f8e3846-043b-4581-a3bd-218f014fcab8" />

3D MODEL:

<img width="605" height="341" alt="Screenshot 2026-10-10 111440" src="https://github.com/user-attachments/assets/e184575b-9c43-4e3b-8371-f03882b7e775" />


DRAFTSMAN

<img width="524" height="368" alt="image" src="https://github.com/user-attachments/assets/30be3a26-8ca4-4dd2-97b7-e36adaacf1e1" />
<img width="523" height="370" alt="image" src="https://github.com/user-attachments/assets/c7a5b015-7523-4694-83c5-6194fc8ce323" />






