### Serial_Simulator

🔣 Software concept for simulating sensor input to Arduino using Python.

#

### CONCEPT

```
import serial
import time
import random

# Establish a serial connection to the Arduino.
# Replace 'COM3' with the correct port name for your system.
ser = serial.Serial('COM3', 9600, timeout=1)
time.sleep(2)  # wait for the serial connection to initialize

# Function to simulate sensor data
def simulate_sensor_data():
    # Generate a random number to simulate sensor data
    return random.randint(0, 1023)

# Main loop to send data to the Arduino
try:
    while True:
        # Simulate the sensor data
        sensor_value = simulate_sensor_data()
        print(f'Sending simulated sensor value: {sensor_value}')
        # Send the simulated sensor data to the Arduino
        ser.write(f'{sensor_value}\n'.encode())
        time.sleep(1)  # wait for a second before sending next data
except KeyboardInterrupt:
    print('Simulation stopped by user')
finally:
    ser.close()  # close the serial connection when done
```

Ensure that you replace 'COM3' with the correct port name that your Arduino is connected to. 

This script will continuously send random sensor values between 0 and 1023 to the Arduino, and you can stop the simulation by pressing Ctrl+C.

### FEATURES

- Reversed serial communication between Python and Arduino.

### REFERENCES

[Pyserial](https://pyserial.readthedocs.io/en/latest/pyserial.html)

### QUESTIONS

Can serial communication between Python and Arduino be reversed?

[Arduino Forum](https://forum.arduino.cc/t/serial-communication-between-python-and-arduino/1158919/4)

##

ℹ️ This software is free and open-source; anyone can redistribute it and/or modify it.
