# Robosoccer-bot

# 🤖 2-Wheel RoboSoccer Bot (Arduino + FlySky)

A differential-drive robosoccer robot controlled using a FlySky FS-i6 transmitter and powered by dual BTS7960 motor drivers.

## 🚀 Features

* Real-time dual-channel RC reading (no pulse loss)
* Smooth differential steering
* Deadband filtering for stable control
* Fail-safe (auto center on signal loss)

## 🧠 Core Concept

Traditional `pulseIn()` fails for multi-channel reading because it blocks execution.
This project solves that by reading both channels simultaneously using edge detection.

## 🧩 Hardware Used

* Arduino Uno
* FlySky FS-i6 Transmitter + Receiver
* 2 × BTS7960 Motor Drivers
* 2 × DC Motors
* 11.1V LiPo Battery
* Buck Converter (5V)

## 🔌 Wiring Overview

### Receiver → Arduino

* CH2 → A0 (Throttle)
* CH4 → A1 (Steering)

### Left Motor Driver

* RPWM → D5
* LPWM → D6
* R_EN → D7
* L_EN → D8

### Right Motor Driver

* RPWM → D9
* LPWM → D10
* R_EN → D11
* L_EN → D12

### Power

* Battery → Motor Drivers (Direct)
* Battery → Buck → 5V → Arduino
* Common Ground Required

## ⚙️ How It Works

1. Reads CH2 (throttle) and CH4 (steering) simultaneously
2. Converts PWM signals into signed speed values
3. Mixes throttle + steering into left/right motor speeds
4. Drives motors using PWM

## 📊 Control Logic

* Forward/Backward → CH2
* Left/Right → CH4
* Differential Drive:

  * Left Motor = Throttle + Steering
  * Right Motor = Throttle - Steering

## 🛠️ Setup Instructions

1. Upload code from `/code/robosoccer_bot.ino`
2. Power system properly
3. Bind FlySky transmitter
4. Calibrate endpoints if needed

## 📷 Diagrams

See `/docs/` for wiring and block diagrams.

## 🧪 Future Improvements

* Add PID for smoother control
* Add IMU for stabilization
* Add autonomous mode

---

Made for RoboSoccer ⚽
