# Low Smart Sensor Module for Real-Time Automatic Switching Device
# 🔌 ESP32-CAM Smart Relay Controller 🚨

A **Low-Power Smart Sensor Module** for real-time automatic switching using **ESP32-CAM**, **PIR sensor**, and **Edge AI** to detect human presence and control electrical loads efficiently.

---

## 📸 Project Overview

This project leverages the ESP32-CAM board's onboard camera and deep sleep functionality to build a low-power, intelligent automation system. It combines **motion detection (PIR)** and **vision-based human detection (Edge Impulse)** to trigger a **relay switch**, optimizing energy usage in real-time.

🧠 Key Features:
- Human detection using camera and PIR sensor
- AI inference using Edge Impulse model
- Relay control based on presence
- Deep Sleep for ultra-low power consumption
- Serial data logging via PuTTY (COM @ 115200 baud)
- Local Access Point server (optional for web dashboard)

---

## ⚙️ Hardware Components

| Component             | Description                                      |
|----------------------|--------------------------------------------------|
| ESP32-CAM            | AI-Thinker module with OV2640 Camera             |
| PIR Sensor           | HC-SR501 for motion detection                    |
| Relay Module         | For switching lights or devices                  |
| HLK-PM01 (5V 2A)     | AC-DC converter (220V to 5V DC)                  |
| Power Supply         | 220V AC Mains                                    |
| Jumper Wires         | For all connections                              |
| Breadboard / PCB     | Prototyping platform                             |

---

## 🧠 AI Model & Dataset

- Trained on human presence detection using **Edge Impulse**
- Balanced dataset with labeled images for `person` and `no person`
- Model Evaluation:
  - **Precision:** 92%
  - **Recall:** 90%
  - **F1 Score:** 91%
- Format: Quantized (int8) model for ESP32-CAM compatibility

---

## 🔌 Modes of Operation

| Mode        | Description                                                                 |
|-------------|-----------------------------------------------------------------------------|
| Idle        | ESP32-CAM in Deep Sleep mode to save power                                 |
| Motion Wake | PIR detects motion → wakes ESP32-CAM                                       |
| Detection   | AI model identifies human presence from camera feed                        |
| Action      | If detected → Relay turns ON; otherwise stays OFF                          |
| Timeout     | No motion detected for 30s → Relay turns OFF and ESP32 goes to sleep again |

---

## 🛠️ Hardware Setup

- **Simulation Diagram**: [Insert diagram]
- **Prototype Board Image**: [Insert image]
- **Serial Outputs**:
  1. No Person Detected
  2. Person Detected via PIR
  3. Person Detected via Camera

Connect to serial monitor using **PuTTY**, set the correct COM port and `115200` baud rate.

---

## 📈 Efficiency Testing

| Test Case                    | Power Consumption | Response Time |
|-----------------------------|-------------------|----------------|
| Deep Sleep Mode             | ~0.01W            | Instant wake via PIR |
| Detection with PIR only     | ~0.5W             | < 1s           |
| Detection with Camera Model | ~1.5W             | ~1.5s          |
| Combined with Relay Trigger | ~2W max           | 1–2s           |

---

## 🔮 Future Scope

- Add mobile/web dashboard for real-time monitoring
- Solar-powered version for remote/off-grid use
- Integration with Google Home / Alexa via MQTT
- Multi-room smart switching with centralized control

---

## 📚 Acknowledgements

Special thanks to **Mr. Rupesh Patel**, **Dr. Sushree Diptimayee Swain**, and all faculty members for guidance, support, and encouragement throughout this project. Gratitude to team members and well-wishers for their contribution and motivation.

---

## 📄 License

This project is licensed under the **MIT License**.  
Feel free to use, modify, and share with attribution.

---

## 🙌 Contribute

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change or add.

---

## 📷 Screenshots

Include images of:
- Your hardware setup
- Serial monitor outputs (with/without person)
- Edge Impulse dashboard or model details

---

> Designed and developed with passion using ESP32-CAM and open-source tools 🔧❤️
