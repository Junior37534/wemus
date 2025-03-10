# Wemus Pro

Wemus Pro is a DIY project for a minimalist and modern little clock, designed to be simple and smart. It displays the time and weather information.

<img src="https://github.com/user-attachments/assets/196e173d-d036-47e8-8ece-8655b3e88b8d" width="600" alt="Wemus"/>
<br>
<a href='https://ko-fi.com/B0B41BFS95' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi1.png?v=6' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

---

The **Wemus Pro** is a sleek, minimalist clock designed to be simple, functional, and easy to use. With a high-contrast 128x64 OLED display, it offers multiple beautiful clock modes that are both modern and clean. You can customize it to turn off automatically and enter deep sleep to save power. The intuitive button on the back lets you switch modes and access a menu with useful features like system info, Wi-Fi status, and even software updates. Every detail was carefully crafted to create a user-friendly experience, making it feel like a commercial product, both in design and performance.

---

# 📋 Table of Contents

- [Features](#-features)
- [Requirements](#-requirements)
- [Required Hardware](#-required-hardware)
- [Firmware Installation](#-firmware-installation)
- [Connection](#-connections)
- [Case](#-case)
- [Assembly](#assembly)
- [Debug](#debug)
- [License](#license)

# ✨ Features

- 128x64 OLED display: Crisp, high-contrast visuals.
- Clean, modern interface: Easy to navigate, designed for beauty and simplicity.
- Multiple clock modes: Beautiful, minimalist options to show the time.
- Deep sleep & auto-off: Save power by setting auto turn-off times.
- Simple button/menu: One button to switch modes and access settings like system info, Wi-Fi status, and more.
- Screensaver: A power-saving display mode.
- Crafted for quality: A sleek, user-friendly design, blending modern aesthetics with practicality.

# 📝 Requirements  

To assemble and use **Wemus Pro**, you’ll need:  

- A computer with **Windows, macOS, or Linux**  
- A **laser cutting machine** (to make the case)  
- **Super glue** (for assembling the case)  
- A **soldering iron and solder** (basic soldering required)  
- A **basic understanding of electronics** (flashing firmware, soldering, and assembly)  

# 🛠 Required Hardware

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
  
<img src="https://media.discordapp.net/attachments/1337152366612582494/1338176299038150756/IMG_6378.jpg?ex=67c32dcb&is=67c1dc4b&hm=ab685dbed31978ad742f79b6cd7bb7cec2e38fac3a7d620a069977ecfc0bd359&=&format=webp&width=1188&height=684" 
  alt="Wemus" width="500" />

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

## Troubleshooting
- If you get permission errors on Linux/macOS:
  ```bash
  sudo chmod 666 /dev/ttyUSB0
  ```
- If the device isn't recognized:
  1. Install/reinstall CH340 drivers
  2. Try a different USB cable
  3. Press and hold FLASH button while connecting the device


# 🏗 Connections

- **VCC** → 5V
- **GND** → GND
- **SDA** → D2
- **SCL** → D1
- **RST** → D0
- **BUTTON1** → D8
- **BUTTON2** → D3

<table>
  <tr>
    <td align="center">
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1337470199582167141/image.png?ex=67c33f30&is=67c1edb0&hm=891cfdf783acbe252e678fe5574d2011c3966d9e6dccff7e43044f2e0452fafe&=&format=webp&quality=lossless&width=722&height=684" width="400" alt="Connections"/>
    </td>
  </tr>
</table>

### ⚠️ **Important:** Most SSD1306 displays support both **3.3V and 5V**, but some models are **3.3V only**. If unsure, try **3.3V first**. If the display doesn’t turn on, use **5V** instead.

### First Boot Configuration

After flashing the firmware and powering on your Wemus Pro for the first time, follow these steps to complete the initial setup:

1. **Connect to Wemus Pro Wi-Fi**

<table>
  <tr>
    <td align="center">
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1337153819103989900/Screenshot_1.png?ex=67c2c149&is=67c16fc9&hm=9c58098488fb36107f91f8486c8e2d0a4d8d1ff23b8048f8103b95a0cfdc0064&=&format=webp&quality=lossless" alt="Finding WemusPro WiFi"/><br>
      <b>Look for "WemusPro" in your Wi-Fi networks</b><br>
    </td>
    <td align="center">
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1345112583975342111/image.png?ex=67c35d37&is=67c20bb7&hm=e466523cb32f5e04a30f8a4c19800a6f826bc4a7dffa3c001d0d2962d8c3618d&=&format=webp&quality=lossless&width=447&height=684" width="400" alt="Configuration Page"/><br>
      <b>Open the IP address in your browser</b><br>
    </td>
  </tr>
</table>

After saving all the settings, the Wemus Pro will restart and attempt to connect to Wi-Fi. If successful, it will determine its geolocation based on the IP address and then restart once more (this only happens once).

![IMG_6384-ezgif com-optimize](https://github.com/user-attachments/assets/adbae029-389b-4207-90da-6325f5798908)

*The flickering on the screen is due to the camera's refresh rate and does not occur in real life.*

Now you can customize your Wemus! 🎉
<table>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/8385427a-23d1-41a4-a68a-c9fc9bd945b8" width="210" alt="WemusModes"/><br>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/6c8e3338-e6b2-4850-bc2f-909adcdea43d" width="210" alt="WemusModes"/><br>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/298f4dd3-f026-4502-9d59-c04f3339ac61" width="210" alt="WemusModes"/><br>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/8c320c58-8861-49fe-a24e-cb9a65528f87" width="210" alt="WemusModes"/><br>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/eda274a7-3c8a-450f-a3c2-0079c6db6d9d" width="210" alt="WemusModes"/><br>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/bc68279a-185a-409b-b952-d240f939af19" width="210" alt="WemusModes"/><br>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/6e9beeba-54cb-442b-9256-bd9f751bf55e" width="210" alt="WemusModes"/><br>
    </td>
    <br>
    You can change the mode by pressing the button and access the configuration by holding it
  </tr>
</table>

## 📦 Case
The case is designed to be laser cut in 3mm material (acrylic or MDF).

<img src="https://media.discordapp.net/attachments/1337152366612582494/1338176947028623451/IMG_6381.jpg?ex=67c32e66&is=67c1dce6&hm=275549435b168e0085b3078d247da9c703d500729bb9fb9d66fbddb049cbf237&=&format=webp&width=815&height=683" alt="Wemus" width="500" />

# Assembly

### 1. Start by **carefully** placing both supports on the display. Pay close attention to avoid damaging the flat cable.  
<table>  
  <td align="center">  
    <img src="https://media.discordapp.net/attachments/1337152366612582494/1346129850322387006/image.png?ex=67c7109e&is=67c5bf1e&hm=d3abac7c5972bd6d86beae2dd36230067dd3ca63181766dcfd7e24d03134da28&=&format=webp&quality=lossless" width="300" alt="Wemus"/>  
  </td>  
</table>  

### 2. Now, insert all four angled feet as shown below.  
<table>  
  <tr>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346133739427725403/image.png?ex=67c7143d&is=67c5c2bd&hm=1fdc9f7e270f69944c6beb8ee51c8b2f50a46865419ae727aa7d33d93dff08cc&=&format=webp&quality=lossless" width="250" alt="Wemus"/>  
    </td>  
    <td>  
      Glue may be necessary.  
      <table>  
        <tr>  
          <td align="center">  
            <img src="https://media.discordapp.net/attachments/1337152366612582494/1346131541348323411/IMG_6539.jpg?ex=67c71231&is=67c5c0b1&hm=405deaad19019c2a280222509bdfec6e06d7b507eae39d1711dbf70d790bf8fd&=&format=webp&width=912&height=684" width="310" alt="Wemus"/><br>  
          </td>  
        </tr>  
        <tr>  
          <td align="center">  
            <img src="https://media.discordapp.net/attachments/1337152366612582494/1346134529865289931/image.png?ex=67c714f9&is=67c5c379&hm=5f4d9d7c73689ab8e86d222051219b07c5b2871d4cdc57ba33fb6cc8f2d4d22d&=&format=webp&quality=lossless&width=550&height=214" width="310" alt="Wemus"/><br>  
          </td>  
        </tr>  
      </table>  
    </td>  
  </tr>  
</table>  

#### ⚠️ Make sure to insert them on the correct side and in the correct orientation.  

### 3. Insert the bottom part on the rear side and glue it to the base.  
I recommend gluing it with the side part attached to ensure proper alignment.  
Then, glue the small piece from the USB hole to lock the Wemus firmly in place.  

<table>  
  <tr>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346136906617851935/IMG_6542.jpg?ex=67c71730&is=67c5c5b0&hm=ffc04c8c3f97ecf526251a40fbcd9f3669f40dffea4fd947a984ed16b9948ee1&=&format=webp&width=912&height=684" width="400" alt="Wemus"/><br>  
    </td>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346144927003840552/image.png?ex=67c71ea8&is=67c5cd28&hm=1c8426890d2e62939b705d23f3fe0b5025543b8353685f456abe7e83e762f3ea&=&format=webp&quality=lossless" width="400" alt="Wemus"/><br>  
    </td>  
  </tr>  
</table>  

### Place the screen and press the front part.
<table>  
  <tr>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346149608857927774/image.png?ex=67c72305&is=67c5d185&hm=920cb3d0a71632800353a7bcb3da5c8f8c1177fadbe8eb05802dee2a548aac5a&=&format=webp&quality=lossless" width="450" alt="Wemus"/><br>  
    </td>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346148425539915906/IMG_6551.jpg?ex=67c721ea&is=67c5d06a&hm=c0ba9b6fc16145c89596157eb979508010114eacc0359963b2d894fad75594a8&=&format=webp&width=513&height=684" width="300" alt="Wemus"/><br>  
    </td>  
  </tr>  
</table>  
The display should be aligned with the frame. Then, you can glue the front part.

### 5. Glue the display holders to lock it in place then wire everything
<table>  
  <tr>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346161594765148320/IMG_6552.jpg?ex=67c72e2e&is=67c5dcae&hm=433e71e284ab8508de8639069785a9fb1dc1ec0808328cd3d8298d41c7a7d72e&=&format=webp&width=912&height=684" width="450" alt="Wemus"/> 
    </td>  
    <td align="center">  
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346170269382873190/IMG_6557.jpg?ex=67c73642&is=67c5e4c2&hm=48366c1dba334e164b40a70ca8879625d4e7d1370657d4384cf7fa1080278f85&=&format=webp&width=912&height=684" width="410" alt="Wemus"/> 
    </td>  
  </tr>  
</table>  
I recommend using at least one of the tools shown below to make it easier to reset the Wemos.
<table>
  <tr>
    <td align="center">
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346167758903181435/IMG_6554.jpg?ex=67c733ec&is=67c5e26c&hm=40036c42bf4cc170e756e498af8bcea4bb8330fcd4ed5edd130dc90f95e87196&=&format=webp&width=912&height=684" width="310" alt="Wemus"/>
    </td>
    <td align="center">
      <img src="https://media.discordapp.net/attachments/1337152366612582494/1346168828647706787/image.png?ex=67c734eb&is=67c5e36b&hm=5c113140172c0972409df08bcbfb3f6fcf28a341de83650ab91c47762779d77c&=&format=webp&quality=lossless" width="260" alt="Wemus"/>
    </td>
  </tr>
</table>

### And finally, test it.
If you want, you can glue the other side, but I highly recommend **not** gluing the top part, the clutch power should be enough to hold it.
Enjoy!

<img src="https://github.com/user-attachments/assets/040d95b5-0250-4a85-bdd3-ba6f97f3dc2a" width="600" alt="Wemus"/>

## Debug
*These are commands that you can run in the terminal on your Wemos D1 Mini clock.*  

- **`ultrareset`** → Erases all saved data.  
- **`sleep`** → Enters deep sleep for 1 minute.  
- **`wifi`** → Displays the current Wi-Fi status (on or off).  
- **`wifion`** → Turns Wi-Fi on.  
- **`wifioff`** → Turns Wi-Fi off.  
- **`-HH:MM-HH:MM`** → Sets deep sleep. The first time is when it sleeps, the second is when it wakes up.  
- **`logATNF`** → Sends logs to the serial monitor if sleep mode is enabled.  
- **`restart`** → Restarts the device.  
- **`check`** → Checks the **WemosOS** version.  
- **`printAll`** → Displays all saved information.  
- **`mode`** → Changes the operating mode.  
- **`font`** → Changes the font style.  
- **`theme`** → Toggles between light and dark mode.  
- **`light`** → Turns the blue LED on or off.  

## 📞 Support

- Open an [Issue](https://github.com/Junior37534/wemus/issues)
- [Learn more about the project](https://wemus-site.web.app/wemus-pro)
- Send an email to <a href="mailto:wemus.dev@gmail.com?subject=Help%20with%20Wemus" target="_blank" rel="noopener noreferrer"><span class="contact-link">wemus.dev@gmail.com</span></a>

---
