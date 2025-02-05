# Wemus Pro

![Wemus Pro](https://media.discordapp.net/attachments/1334952524570038284/1336460345623056466/IMG_3775.jpeg?ex=67a3e330&is=67a291b0&hm=7e5159a1bfc85dc614bba14bc8388ac06f84e598edea4b49344fa590f63c7048&=&format=webp&width=895&height=671)

Wemus Pro is a DIY project for a minimalist and modern little clock, designed to be simple and smart. It displays the time and weather information.

## 📋 Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Required Hardware](#required-hardware)
- [Assembly](#assembly)
- [Case](#case)
- [FAQ](#faq)
- [License](#license)

## ✨ Features

- High contrast 128x64 OLED display
- Based on Wemos D1 Mini (ESP8266)
- Customizable laser-cut case
- Intuitive interface
- Low power consumption
- Wi-Fi connectivity

## 📝 Requirements  

To assemble and use **Wemus Pro**, you’ll need:  

- A computer with **Windows, macOS, or Linux**  
- A **laser cutting machine** (to make the case)  
- **Super glue** (for assembling the case)  
- A **soldering iron and solder** (basic soldering required)  
- A **basic understanding of electronics** (flashing firmware, soldering, and assembly)  

## 🛠 Required Hardware

<table>
  <tr>
    <td align="center">
      <a href="https://www.aliexpress.com/item/32651747570.html">
        <img src="https://ae-pic-a1.aliexpress-media.com/kf/S32da1b4aaefe4a7d9111f49bbbba9832h.jpg_960x960q75.jpg" width="200" alt="Wemos D1 Mini"/><br>
        <b>Wemos D1 Mini</b>
      </a>
    </td>
    <td align="center">
      <a href="https://www.aliexpress.com/item/32896971385.html">
        <img src="https://ae-pic-a1.aliexpress-media.com/kf/S109766c9012c4ba6818abf7ab9e2de03I.jpg_960x960q75.jpg" width="200" alt="Display OLED SSD1306"/><br>
        <b>OLED Display SSD1306 128x64 I2C</b>
      </a>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://pt.aliexpress.com/item/32726768571.html">
        <img src="https://ae-pic-a1.aliexpress-media.com/kf/HTB1e0fNkvBNTKJjSszeq6Au2VXan.jpg_960x960q75.jpg" width="200" alt="Push Button 12mm"/><br>
        <b>Push Button 12mm</b>
      </a>
    </td>
    <td align="center">
      <a href="https://www.aliexpress.com/item/32825083543.html">
        <img src="https://ae-pic-a1.aliexpress-media.com/kf/S422c5543f861406897e211457b1d3517R.jpg_960x960q75.jpg" width="200" alt="Jumper Wires"/><br>
        <b>Jumper Wires</b>
      </a>
    </td>
  </tr>
</table>

- **1x Wemos D1 Mini**  
- **1x SSD1306 I2C 128x64 OLED display**  
- **1x 12mm push button**  
- **7x Jumper wires**  
  - **4x** for connecting the display  
  - **2x** for the button  
  - **1x** for connecting **D0 to RST** (required for sleep mode)  
- **1x 3mm MDF board (HDF also works, untested with acrylic)**  

# 📥 Firmware Installation
1. Download the latest firmware: [wemus_os.ino.bin](https://github.com/Junior37534/wemus/blob/main/firmware/wemus_os.ino.bin)  
2. To install the firmware on your Wemos D1 Mini, use one of the following tools:  

### 1️⃣ Option 1: ESPHome Web Flashing (Easier)

1. Plug the Wemos D1 Mini into your PC via USB.

2. Go to [https://web.esphome.io/](https://web.esphome.io/) and click **Connect**.

3. Select the correct COM port that your Wemos D1 Mini is connected to.

4. Click **Install**, browse for the `wemus_os.ino.bin` file on your computer, and then click **Flash**.

5. The flashing process will take a moment. Once finished, the device will reboot.

### 2️⃣ Option 2: ESP Flash Download Tool  
1. Install [Python](https://www.python.org/downloads/) and esptool if you haven't already:
   ```bash
   pip install esptool
   ```
2. Connect your Wemos D1 Mini and identify the COM port:
   - Windows: Check Device Manager under "Ports (COM & LPT)"
   - Linux: Run `ls /dev/tty*` (usually appears as `/dev/ttyUSB0`)
   - macOS: Run `ls /dev/cu.*` (usually appears as `/dev/cu.usbserial-*`)

3. Flash the firmware using esptool:
   ```bash
   # Erase flash memory
   esptool.py --port COM3 erase_flash
   
   # Windows
   esptool.py --port COM3 --baud 115200 write_flash 0x0 wemus_os.ino.bin

   # Linux/macOS
   esptool.py --port /dev/ttyUSB0 --baud 115200 write_flash 0x0 wemus_os.ino.bin
   ```

**Note:** Replace `COM3` or `/dev/ttyUSB0` with your actual device port.

### Troubleshooting
- If you get permission errors on Linux/macOS:
  ```bash
  sudo chmod 666 /dev/ttyUSB0
  ```
- If the device isn't recognized:
  1. Install/reinstall CH340 drivers
  2. Try a different USB cable
  3. Press and hold FLASH button while connecting the device


## 🏗 Connections

- **VCC** → 5V
- **GND** → GND
- **SDA** → D2
- **SCL** → D1
- **RST** → D0
- **BUTTON1** → D8
- **BUTTON2** → D3

### ⚠️ **Important:** Most SSD1306 displays support both **3.3V and 5V**, but some models are **3.3V only**. If unsure, try **3.3V first**. If the display doesn’t turn on, use **5V** instead.


### Assembly Tips

- Check connection polarity before soldering
- Use different colored wires for easier identification
- Make connections with the device powered off
- Test all connections before assembling the case

## 📦 Case

The case is designed to be laser cut in 3mm material (acrylic or MDF).

## ❓ FAQ

### The display doesn't turn on, what should I do?
Check the connections and make sure you're using the correct voltage.

### Can I use a different OLED display?
Yes, as long as it's I2C compatible and has 128x64 resolution.

### Can the case be 3D printed?
Currently we only provide laser cutting files, but you can create your own 3D version.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 📞 Support

- Open an [Issue](https://github.com/Junior37534/wemus/issues)
- Send an email to [wemus.dev@gmail.com]

---
