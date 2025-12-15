# CSN150-ESP32-AP-Docs[README.md](https://github.com/user-attachments/files/23638483/README.md)
# Cybersecurity : CSN150

Project: ESP32 Access Point Web Server

## Purpose

I made my ESP32-CAM act like a fake WiFi hotspot (Access Point) with a secret web page you can visit. It's like turning your toy robot into a mini internet cafe! Followed the guide from Random Nerd Tutorials to learn how WiFi works behind the scenes. No real internet — just local tricks for school.

## Equipment

- None! I used Wokwi.com (free online ESP32 simulator) because I don't have a physical ESP32-CAM yet. Super safe and easy!

## Links to documentation and tools

##### Video 1:
- Wokwi Project (live demo): [Paste your Wokwi link here, like https://wokwi.com/projects/123456789]
- Main Guide: https://randomnerdtutorials.com/esp32-cam-access-point-ap-web-server/

##### Other Links:
- Arduino IDE (if you want to try real code): https://www.arduino.cc/en/software
- Wokwi ESP32 Start: https://wokwi.com/projects/new/esp32

##### AI GPTs used
- Grok (that's me! Built by xAI) — helped me paste code and fix steps like a robot buddy.

## Steps I followed

1. Opened Wokwi.com and clicked "Start from Scratch" > picked ESP32 (close enough to ESP32-CAM for sim).
2. Deleted the default code in sketch.ino.
3. Copied the Access Point code from the Random Nerd Tutorials guide (tweaked for no camera since Wokwi doesn't have one).
4. Changed SSID to "ESP32-CAM-AP" and password to "12345678".
5. Clicked the green Play button — boom, Serial Monitor showed the output you pasted!
6. In Wokwi, "connected" to the fake WiFi (right side) and visited http://192.168.4.1 in the pretend browser — web server page loaded with a hello message.
7. Took screenshots (Serial output, WiFi connect, web page).
8. Downloaded the GitHub template ZIP, edited README.md with my story, and uploaded to my own GitHub repo.

## Problems and Solutions

Problem: Wokwi doesn't have a real "ESP32-CAM" part or camera — the code had camera stuff that crashed.  
Solution: I cut out the camera init lines (like #include "esp_camera.h" and camera_config_t) and just kept the WiFi AP + web server. Works perfect in sim! (Real hardware would need FTDI wires, but sim skips that.)

Problem: No WiFi Router part showed up at first in Wokwi.  
Solution: Used the direct link https://wokwi.com/projects/new/esp32?template=wifi-router — it added one automatically. Set SSID to match my fake one.

Problem: Web page didn't load right away.  
Solution: Restarted the sim (red Stop button > green Play). Wokwi sometimes needs a coffee break. 😄

### Example Problem (from template)
Problem: Arduino code will not load on ESP32 Cam.  
Solution: (Didn't happen to me in sim, but guide says install CH341SER driver for real USB: https://www.wch-ic.com/downloads/CH341SER_ZIP.html)

## Final Report

This project was awesome — like giving my ESP32 superpowers to make its own WiFi! In Wokwi, it started the AP in seconds, and connecting showed a simple web page saying "Hello from ESP32!" (I added that). Learned WiFi APs are easy to fake, which is why passwords matter. Total time: 45 minutes. If I had real hardware, I'd add the camera stream next. Score: 10/10 robot points! Ready for class demo — just share my Wokwi link. 🎉

## About

---

## 🔧 Troubleshooting & Challenges

### Challenge 1: Compilation Timeouts
*   **Issue:** Initially attempted to use C++ (Arduino framework), but the free tier of the Wokwi build servers was overloaded, causing "Build Server Busy" errors.
*   **Solution:** Pivoted to **MicroPython**. Since Python is interpreted directly in the browser, it bypasses the heavy compilation queue, allowing for instant and reliable simulation testing.

### Challenge 2: LED Visibility
*   **Issue:** The LED blink was initially too fast (50ms) to see clearly in the simulation.
*   **Solution:** Adjusted the `time.sleep()` duration from `0.05` to `0.5` seconds to make the visual alert distinct and clear in the demonstration video.

## 📸 Proof of Concept
![Simulation Screenshot](https://i.postimg.cc/Bn7n4x7z/image.png)
A Documentation Template for projects you complete in CSN150 (I filled it with my ESP32 AP story!)
