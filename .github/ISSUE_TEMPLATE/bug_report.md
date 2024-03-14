---
name: Bug report
about: 38 pins ESP32-WROOM-32
title: ESP32-WROOM-32 38 pins
labels: bug, question
assignees: njhjgyj

---

I have an 38 pins ESP32-WROOM-32  i attach it to my computer and laptop using USB after connecting the blue light is start blinking on the G2 pin after that i open the arduino ide and in the select board option its not showing any ports and the port is also not showing in the device manager so i install CP210x driver after that the port is showing in the device manager "Silicon Labs CP210x USB to UART Bridge (COM5)" and in the Arduino ide in the select board option the port is showing "COM5" but the board nake is Unknown so i go to file, prfrences and attach that "https://dl.espressif.com/dl/package_esp32_index.json" URL and after that i go to tools, board, board manager and install the esp32 by espressif system but the problem is same so i instal additional drivers like "CH9102_Driver-main, CDM21364_Setup" but the problem is same so i try to flash my esp32 board using esptool.py but its giving an error

esptool.py v4.7.0
Serial port COM5
Connecting.........
Chip is ESP32-D0WD-V3 (revision v3.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: d4:8a:fc:a8:38:08
Uploading stub...
Running stub...
Stub running...
WARNING: Failed to communicate with the flash chip, read/write operations will fail. Try checking the chip connections or removing any other hardware connected to IOs.
Configuring flash size...
Flash will be erased from 0x00001000 to 0x00168fff...
Compressed 1473376 bytes to 963340...

A fatal error occurred: Packet content transfer stopped (received 8 bytes)

And there is one more thing after i use that "python -m esptool --chip esp32 --port COM5 write_flash -z 0x1000 espruino_2v21_esp32.bin" command to flash my esp32 then the blue light on the esp32 is turned off and after that i press the RST button on the esp32 then the blue is turned on and start blinking i don't know what is the meaning of that i try to hold BOOT button on the esp32 and after entering that "python -m esptool --chip esp32 --port COM5 write_flash -z 0x1000 espruino_2v21_esp32.bin" command the connecting is shown on the terminal so i release the BOOT button but the problem is still same i open Arduino IDE and manually select the board "ESP32 Dev Module" and upload the code but its giving an error

Sketch uses 230493 bytes (17%) of program storage space. Maximum is 1310720 bytes.
Global variables use 20968 bytes (6%) of dynamic memory, leaving 306712 bytes for local variables. Maximum is 327680 bytes.
esptool.py v4.5.1
Serial port COM5
Connecting...........
Chip is ESP32-D0WD-V3 (revision v3.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: d4:8a:fc:a8:38:08
Uploading stub...
Running stub...
Stub running...
Changing baud rate to 921600
Changed.
WARNING: Failed to communicate with the flash chip, read/write operations will fail. Try checking the chip connections or removing any other hardware connected to IOs.
Configuring flash size...
Flash will be erased from 0x00001000 to 0x00005fff...
Flash will be erased from 0x00008000 to 0x00008fff...
Flash will be erased from 0x0000e000 to 0x0000ffff...
Flash will be erased from 0x00010000 to 0x00048fff...
Compressed 18992 bytes to 13112...

A fatal error occurred: Packet content transfer stopped (received 8 bytes)
Failed uploading: uploading error: exit status 2

In my code i don't write anything in that code the code is 

void setup() {
  // put your setup code here, to run once:

}

void loop() {
  // put your main code here, to run repeatedly:

}


but the error is same and after selecting the board "ESP32 Dev Module" i go to tools, and click the get board info then its giving an BN: Unknown Board

BN: Unknown board
VID: 0x10C4
PID: 0xEA60
SN: 0001

i try to power the esp32 using power adapter i set the power adapter to the 4.5V and the + wire of the power Adapter i connect it to V5 pin of the esp32 and - wire of the power adapter i connect it to GND of the esp32 and attach the USB with my computer and upoad the code but the problem is still same i try to change the USB cable and USB port and my computer i use that in my laptop too but the problem is same.

Can anyone help me my device specification is

Processor	AMD Ryzen 7 4700U with Radeon Graphics            2.00 GHz
Installed RAM	16.0 GB (15.4 GB usable)
Device ID	4B6A925B-96E8-4EA3-A477-B4ACECCD9C5E
Product ID	00325-96690-41418-AAOEM
System type	64-bit operating system, x64-based processor
Pen and touch	No pen or touch input is available for this display

And the windows is 11.
