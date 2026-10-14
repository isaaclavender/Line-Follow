# Line-Follow

A line-following robot built on a Raspberry Pi 4B, written in Python with `RPi.GPIO`.

## How it works

Three infrared sensors read the line position as a pattern (left, middle, right), and the robot picks an action:

- Middle sensor on the line, or no line seen: drive forward
- Line on the left: pivot left until the line is centred again
- Line on the right: pivot right until the line is centred again
- All three sensors on the line: stop

Motor speed is set with PWM. The robot also has an ultrasonic sensor and left/right obstacle sensors, which are read but not yet used to avoid obstacles.

## Running

Requires `RPi.GPIO`.

```
sudo python3 line-follow.py
```

Press `Ctrl+C` to stop the motors and clean up the GPIO pins.
