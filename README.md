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

- Computer with Windows, macOS or Linux
- Laser cutting machine (optional)
- Super glue
- Soldering iron and solder (basic)

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

- 1x [Wemos D1 Mini]
- 1x [SSD1306 I2C 128x64]
- 1x 12mm Push button
- 6x Jumper wires (4x for connecting the display to Wemos and 2x for the button)
- 1x MDF board
- Connection wires
- Case material (3mm acrylic or MDF recommended)

## 📥 Firmware Installation

1. Download the latest .bin file from the [releases section](https://github.com/seu-usuario/Junior37534/releases)
2. To flash the firmware, you can use:
   - [ESPHome Flasher](https://github.com/esphome/esphome-flasher/releases) (Recommended for beginners)
   - [ESP Flash Download Tool](https://www.espressif.com/en/support/download/other-tools)

### Flashing Instructions

1. Connect the Wemos D1 Mini to your computer via USB
2. Open your chosen flashing software
3. Select the correct COM port
4. Load the .bin file
5. Start the flashing process

## 🏗 Assembly

| **Display OLED** | **Wemos D1 Mini**   |
|-----------------|--------------------|
| **SDA** | D2 |
| **SCL** | D1 |
| **VCC** | 5V |
| **GND** | GND |

| **Button** | **Wemos D1 Mini**   |
|-----------------|--------------------|
| **BUTTON1** | D8 |
| **BUTTON2** | D3 |
| **RST** | D0 |


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
- Join our [Discord](https://discord.gg/seu-servidor)
- Send an email to [wemus.dev@gmail.com]

---
