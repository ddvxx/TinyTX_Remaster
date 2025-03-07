# TinyTX_Remaster
This project was made for the necesity of having an smaller radio transmitter for flying FPV drones.

![WhatsApp Image 2025-03-07 at 20 43 42 (2)](https://github.com/user-attachments/assets/638d84ba-e9f9-4e2f-adbd-da8869b4e15a)

Following (This repo)[https://github.com/dbloemhard/Arduino-Transmitter-for-ELRS3.x] instructions, we are able to have an ELRS transmmiter using arduino and a receiver of the same protocol with almost no tweaks on the code.

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
- 🏗️ **3D-printed enclosure and multiple electronic components**
  
---

## ⚙️ Building the transmitter

### 📡 Flashing the Receiver as a Transmitter  

There are multiple ways to flash a receiver:
- Connecting to its **WiFi**
- Using **Betaflight Passthrough**
- Using a **USB-TTL programmer**  

The **USB-TTL method** was chosen for convenience.  

## 🛠️ Preparation  
1. **Verify** the receiver works by connecting it to a flight controller.  
2. **Boot up** the receiver and wait for its **WiFi** to activate.  
3. **Backup Configuration**:  
   - Connect to the receiver’s WiFi.
   - Navigate to `10.0.0.1/hardware.json`.
   - Save this file—it contains the receiver’s configuration (**similar to a Betaflight CLI Dump**).  

## ⚡ Flashing Process  
- The **ExpressLRS Configurator** does not support DIY devices. Instead, use the **web flasher**:  
  🔗 [ExpressLRS Web Flasher](https://expresslrs.github.io/web-flasher/)  

### **Steps:**  
1. **Select:**  
   - **DIY Devices** → **2.4GHz Transmitter** → **Generic ESP8285 Full-duplex 2.4GHz RX as TX**  
   - Choose the **flashing method**  
   - Add **bind phrase** and **WiFi configuration** (leave UART inversion **disabled**)  

## 🔄 Final Steps of flashing
1. After flashing, **wait for WiFi to start again**.  
2. Navigate to `10.0.0.1/hardware.html` (**slightly different from the backup location**).  
3. **Upload the saved JSON file** and click **Update**.  
4. A confirmation message should appear.  
5. **Power cycle** the device if needed to apply changes.  

This ensures the new **TX module** has the correct power output settings. 🚀



---

  ## 📷 Connection Diagram
![image](https://github.com/user-attachments/assets/879a0a09-864c-408a-a9f9-d6e28188bd27)

---

## 🖥️ Base Code
(Code)[https://github.com/dbloemhard/Arduino-Transmitter-for-ELRS3.x/blob/main/SimpleTX/SimpleTX.ino] from the repo I mentioned earlier.

---

## 🚁 The Drone
All the drones I make, are by spare components. I usually fix some broke ones by replacing defective PCB parts. For this one, I fixed one broken Crazybee F3. The motor i used are 4 Happymodel RS0802 20000KV. All mixed with the ELRS 2.4 GHz receiver, frame, camera and video transmitter, we have a pretty good build to fly indoors or even outdoors.
![image](https://github.com/user-attachments/assets/3cd236d1-8e83-40b8-b545-8468eef983e3)
![image](https://github.com/user-attachments/assets/43e33f4e-0e09-4273-a1d5-ba896a9ea104)
![image](https://github.com/user-attachments/assets/de7011cf-ff7b-4bc3-aec6-f6c49b0dfab8)

---

## 🏆 Conclusion
Thanks to (Tokyo_Dom)[https://www.thingiverse.com/thing:6677484] and (dbloemhard)[https://github.com/dbloemhard] for their works on such a good guide. Let's fly! 🚁✨


