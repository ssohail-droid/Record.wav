# Record.wav
A standalone ESP32 audio player that streams CD-quality WAV files from an SD card to Bluetooth headphones or speakers. Includes smooth A2DP transmission, a ring-buffered audio pipeline, a 128×128 OLED UI, volume control, next/pause functions, and a simple physical control interface.

## Required Components & Tools:
- ESP32-WROOM-32 Development Board
(Recommended: 8 MB Flash version — stable for Bluetooth A2DP)
- SD Card Module (SPI-based)
Compatible with 3.3V logic
Example: HW-125, Catalex, or any generic SPI SD reader
- MicroSD Card (FAT32 formatted)
- SH1107 or SSD1306 128×128 OLED Display (I²C)
4-pin version (GND, VCC, SDA, SCL)
- WAV-compatible Bluetooth headphones or speakers
ESP32 streams via A2DP sink mode


## Step 1: Print the Case

### [Download the print here](https://github.com/ssohail-droid/Record.wav/tree/main/STL)

## Step 2: Wiring

| ESP32 Pin | OLED Pin |
| --------- | -------- |
| 3.3V      | VCC      |
| GND       | GND      |
| GPIO21    | SDA      |
| GPIO22    | SCL      |

| ESP32 Pin | SD Module Pin |
| --------- | ------------- |
| GPIO5     | CS            |
| GPIO18    | SCK           |
| GPIO23    | MOSI          |
| GPIO19    | MISO          |
| 3.3V      | VCC           |
| GND       | GND           |

| Function   | ESP32 Pin | Second Leg |
| ---------- | --------- | ---------- |
| Play/Pause | GPIO25    | GND        |
| Next Track | GPIO14    | GND        |
| Volume −   | GPIO27    | GND        |
| Volume +   | GPIO26    | GND        |

## Step 3: Programming

