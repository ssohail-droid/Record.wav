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

### Complete Wiring Overview (Side-by-Side)

| OLED Wiring (ESP32 → OLED) | SD Module Wiring (ESP32 → SD) | Button Wiring (Function → Pin → GND) |
| -------------------------- | ----------------------------- | ------------------------------------ |
| 3.3V → VCC                 | GPIO5  → CS                   | Play/Pause → GPIO25 → GND            |
| GND  → GND                 | GPIO18 → SCK                  | Next Track → GPIO14 → GND            |
| GPIO21 → SDA               | GPIO23 → MOSI                 | Volume − → GPIO27 → GND              |
| GPIO22 → SCL               | GPIO19 → MISO                 | Volume + → GPIO26 → GND              |
|                            | 3.3V → VCC                    |                                      |
|                            | GND → GND                     |                                      |


## Step 3: Programming

### [Get the code here](https://github.com/ssohail-droid/Record.wav/blob/main/Code/BT-Code)

- Upload the code from the Arduino IDE and flash it to the board.

## Step 4: Get the music

- Disclaimer: This WAV player project does not support or encourage piracy. All audio used should be legally obtained.
- This WAV player only supports `.wav` files. I personally like using this website:
### [Here](https://www.freeconvert.com/mp3-to-wav)
-Then upload the music onto the SD card.

## Congratulations! You now have Record.wav!!!!!!.


<p align="center">
  <a href="https://example.com">
    <img src="https://media.tenor.com/3_mXIoBPNhoAAAAi/party-parrot.gif" alt="Demo GIF">
  </a>
</p>

