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


                           ┌─────────────────────────┐
                           │     ESP32 DEVKIT V1     │
                           │                         │
        3.3V  ─────────────┤3V3                  VIN ├──── (not used)
        GND   ─────────────┤GND                  GND ├──────────────┐
                           │                         │              │
        SDA ───────────────┤GPIO21               IO23┤──── MOSI ----┼──── SD MOSI
        SCL ───────────────┤GPIO22               IO19┤──── MISO ----┼──── SD MISO
                           │                         │              │
 SD CS  ───────────────────┤GPIO5                IO18┤──── SCK  ----┼──── SD SCK
                           │                         │
 BTN PLAY ────────┐        │                         │
                  │   ┌────┤GPIO25               IO5 ┤──── SD CS
                  │   │    │                         │
 BTN NEXT ────────┼───┤GPIO14                      ┌─┤EN (ignore)
                  │   │                            │
 BTN VOL- ────────┼───┤GPIO27                      │
                  │   │                            │
 BTN VOL+ ────────┼───┤GPIO26                      │
                  │   │                            │
                  │   │                            │
                  │   └────────────────────────────┘
                  │
                 GND (common ground for all buttons)


──────────────────────────────────────
 OLED (SH1107 128×128 I²C)
──────────────────────────────────────
 OLED VCC  ─────────── 3.3V  
 OLED GND  ─────────── GND  
 OLED SDA  ─────────── GPIO21  
 OLED SCL  ─────────── GPIO22  


──────────────────────────────────────
 SD Card Module (SPI)
──────────────────────────────────────
 SD VCC   ─────────── 3.3V  
 SD GND   ─────────── GND  
 SD CS    ─────────── GPIO5  
 SD SCK   ─────────── GPIO18  
 SD MOSI  ─────────── GPIO23  
 SD MISO  ─────────── GPIO19  



