# TinyTX_Remaster
This project was made for the necesity of having an smaller radio transmitter for flying FPV drones.

![WhatsApp Image 2025-03-07 at 20 43 42 (2)](https://github.com/user-attachments/assets/638d84ba-e9f9-4e2f-adbd-da8869b4e15a)

Following [This repo](https://github.com/dbloemhard/Arduino-Transmitter-for-ELRS3.x) instructions, we are able to have an ELRS transmmiter using arduino and a receiver of the same protocol with almost no tweaks on the code.

# 🚁 Project: Drone Transmitter with Arduino 🚀

## 📌 Description
This project aims to develop a **radio frequency transmitter** to control drones using **Arduino and ELRS protocol**. The transmitter will be using the capabilities of some ELRS receiver to transmit data for the telemetry to be able to connect to the drone.

---

## 🛠️ Required Materials
📦 **Main Components:**
- 🖥️ **Arduino Nano**
- 📡 **ExpressLRS Nano receiver, the one with a 100mw PA (or even more)** (for wireless communication)
- 🎮 **Analog Joystick and switches, extracted from a FlySky FS-i6 tx** (for directional control and aux channels functions)
- 🔋 **Battery and voltage regulator module**
- 🏗️ **3D-printed enclosure (Custom one for the TX Sticks measurements in the repo) and multiple electronic components**
  
---

## ⚙️ Building the transmitter
### 1. Flash the ELRS Receiver as a TX
There are several ways to flash the receiver: connecting to its WiFi, using Betaflight Passthrough with a flight controller, or a USB-TTL programmer. I used the USB-TTL since I had it available.

Before flashing, it's a good idea to connect it to a flight controller to confirm it works as a receiver. To turn it into a transmitter, first power it on and wait for it to enable WiFi. Then, connect to its network, go to `10.0.0.1/hardware.json`, and back up the file—this contains its configuration (similar to a CLI Dump in Betaflight).

ExpressLRS Configurator doesn’t support DIY devices, but you can use the **[web flasher](https://expresslrs.github.io/web-flasher/)** instead.

Steps:
1. Select **DIY devices** → **2.4GHz transmitter** → **Generic ESP8285 Full-duplex 2.4GHz RX as TX**.
2. Choose the flashing method, enter your bind phrase and WiFi settings (don’t change "Invert UART").
3. After flashing, wait for WiFi to start again and go to `10.0.0.1/hardware.html` (note the slight URL change).
4. Upload the saved JSON file and hit "Update" to restore the configuration and ensure correct power output.

In my case, the RX (now TX) needed to be power cycled.

### 2. Cable soldering and connections
Just connect all together as in the image below, in the next section.

![image](https://github.com/user-attachments/assets/5d5b8d23-89f5-4b8e-a004-c6d16dd92b39)
![image](https://github.com/user-attachments/assets/ab60d3c0-72d6-422c-ba79-020177e55635)

### 3. Flash the Arduino Nano
Once you've assembled it, it's time to flash the Arduino. Visit [this GitHub link](https://github.com/dbloemhard/Arduino-Transmitter-for-ELRS3.x), click the green "Code" button, and choose "Download ZIP" (or clone the repository if you're familiar with that process). You only need the `SimpleTX` folder from the download.

Open Arduino IDE and load `SimpleTX/SimpleTX.ino` (or double-click the `.ino` file).

### In the Arduino IDE:
1. Under the **Tools** menu, choose **Board** → **Arduino AVR boards** → **Arduino Nano**.
2. Set **Programmer** to **AVR ISP MkII**.
3. Go to **Tools** → **Processor** → **Atmega328p (old bootloader)**.
4. Finally, select the correct port that appears when you connect your Arduino.

You should now be able to upload the sketch to the Arduino.

Once calibrated, just plug a 2 cells battery, and we are able to go.

---

  ## 📷 Connection Diagram
![image](https://github.com/user-attachments/assets/879a0a09-864c-408a-a9f9-d6e28188bd27)

---

## 🚁 The Drone
All the drones I make, are by spare components. I usually fix some broke ones by replacing defective PCB parts. For this one, I fixed one broken Crazybee F3. The motor i used are 4 Happymodel RS0802 20000KV. All mixed with the ELRS 2.4 GHz receiver, frame, camera and video transmitter, we have a pretty good build to fly indoors or even outdoors.
![image](https://github.com/user-attachments/assets/3cd236d1-8e83-40b8-b545-8468eef983e3)
![image](https://github.com/user-attachments/assets/43e33f4e-0e09-4273-a1d5-ba896a9ea104)
![image](https://github.com/user-attachments/assets/de7011cf-ff7b-4bc3-aec6-f6c49b0dfab8)

---

## 🏆 Conclusion
Thanks to [Tokyo_Dom](https://www.thingiverse.com/thing:6677484) and [dbloemhard](https://github.com/dbloemhard) for their works on such a good guide. Let's fly! 🚁✨


