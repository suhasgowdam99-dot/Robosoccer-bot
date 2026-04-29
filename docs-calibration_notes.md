# 🎯 Calibration Notes

## PWM Range (Observed)

* Min: ~997
* Center: ~1496
* Max: ~1988

## Deadband

* Set to 40 to eliminate joystick noise

## Why Calibration Matters

Accurate mapping ensures:

* Smooth motion
* No drift when joystick is centered
* Full-speed utilization

## How to Recalibrate

1. Print raw PWM values via Serial
2. Move sticks to extremes
3. Update constants in code
