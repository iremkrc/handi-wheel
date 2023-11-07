# Hand-Assisted Navigation for Disabled Individuals with Wheelchair (HANDI-WHEEL)

**Group Members**
- İrem Karaca
- Arda Gürsul
- Birkan Çelik

**Team Name:** Tech Tribe

## Overview

HANDI-WHEEL provides a wheelchair for disabled people that is controlled by basic hand movements. The project aims to help people who have difficulties maneuvering their wheelchairs and make their life easier. It uses a microcontroller and an acceleration sensor to set the direction of the wheelchair. The wheelchair can be directed by gentle hand movements due to the sensitivity of the system. A small prototype for the wheelchair and a smart glove that covers the microcontroller and acceleration sensor will be provided at the end of this project. This project required multidisciplinary work throughout designing and building and provided human-computer interaction.

<img width="476" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/c9058118-8574-4300-9d0a-2311ad38021e">
<img width="476" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/7f36a59f-c6d6-495a-b84c-5680e437703f">


## Goals

- Designing a wheelchair that can be controlled using hand gestures.
- Making a controller that can be used wirelessly.
- Realizing a proof of concept model.
- Presenting MVP (Minimum Viable Product).

## Impact

- Users will be able to use their wheelchairs wirelessly.
- The wheelchair will be able to come to the user within range.
- The user will be able to control the wheelchair with basic hand gestures. There is no need for rolling the wheels anymore.
- There are approximately 2 Million wheelchair users in our country. We propose that almost 2-3% of them will use our gesture-controlled system at first glance.

## List of Components

- x2 Arduino UNOs
- x2 Wheels
- Ball Caster Wheel
- x2 Wireless NRF24L01 2.4 GHz Transceiver Modules
- L298N Dual H-Bridge Motor Driver
- x2 9V Batteries
- Adafruit BNO055 Absolute Orientation Sensor
- Jumper Wires
- x2 Electric Motors

### Smart Glove

The smart glove consists of an Arduino UNO, an NRF24L01 module, a 9V battery, and a BNO055 orientation sensor.

<img width="401" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/10584ba6-231a-4afd-b0c2-fd761acd0c8f">
<img width="401" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/5c911127-e7e8-43c6-8ae9-eef8777f9df2">


The BNO055 orientation sensor is a compact chip that combines an accelerometer, gyroscope, and magnetometer. Its primary function is to provide accurate and reliable orientation information in three-dimensional space. In our project, the BNO055 orientation sensor detects the hand gestures of the user. By its working principle, it calibrates its origin according to the first initialization position. Then the movements are perceived according to this origin. The sensor is attached to a small breadboard so that it is stable and minimizes the noise that can lead to non-intended hand movements. The NRF24L01 module is a popular wireless communication module that operates on the 2.4 GHz frequency band. It utilizes the RF (radio frequency) protocol to establish a wireless link between two or more NRF24L01 modules. In our project, communication occurs between two NRF24L01 modules. We chose this module because it requires low power consumption and is low cost. NRF24L01 module sends the collected data to the wheelchair to achieve movement. It gets the roll, pitch, and yaw movement data. Puts them in a struct and sends them to the wheelchair. The data sent is quite compact and only necessary information is sent. The detailed implementation can be seen in the code provided below. To use the NRF24L01 module, we connected it to an Arduino UNO microcontroller. Also, the communication that is held between the modules is short-range which makes the NRF24L01 module an ideal choice for our project because we know that the data will be sent from the person's smart glove, sitting on the HANDI-WHEEL, to the chair.

## Wheelchair

The wheelchair consists of an Arduino UNO, 2 wheels, a ball caster wheel, an L298N dual motor driver, an NRF24L01 module, a 9V battery, and 2 electric motors.

<img width="335" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/0f36c140-7ec3-458f-b56e-dcf91d21a932">
<img width="335" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/60f6a86b-f8f7-4852-9bc8-57fa879406e3">


The wheelchair receives the orientation values from the smart glove through the NRF24L01 module. The Arduino UNO sends the movement signal to the L298N dual motor driver according to the orientation sensor values. The L298N is a dual H-bridge motor driver integrated circuit (IC). It is commonly used to control the direction and speed of two DC motors. The L298N is capable of driving high-current loads which makes it suitable for our project. In our project, the L298N dual motor driver gets power from the 9V battery and sets the voltage level at 5V. Then the electric motor/s start to spin in the direction of the command they are given. This can be "go ahead", "go back", "turn left", or "turn right".

## Future Work

In future work, we propose implementing an ultrasonic sensor to the back of the HANDI-WHEEL. The sensor would basically warn the user in case of any collusion danger. One more addition that we can add is another Bluetooth module so that it is easily connected to a smartphone. This way the user would be able to control the HANDI-WHEEL with their smartphone without even needing an external component. Also, voice recognition can be used to convert the commands of the user to the predefined serial commands to the receiver in the HANDI-WHEEL. This way users could even be able to use the wheelchair by just talking. In that regard, we formerly made a code and demo that we control the motors with voice commands. That means the concept is proven by TechTribe with just implementing left behind.

## Demonstration

[Koç University - Tech Tribe - ENGR429 Final Project Demo](https://youtu.be/MgdQEN-yoqo)

[Koç University - Tech Tribe - ENGR429 Final Project Demo 2](https://youtu.be/Bat1IvMvZbA)

## Presentation

[**https://www.canva.com/design/DAFlIyHRwDQ/2gYpp4BeYeHoo7OYXn4Ndg/view?utm\_content=DAFlIyHRwDQ&utm\_campaign=designshare&utm\_medium=link&utm\_source=publishsharelink**](https://www.canva.com/design/DAFlIyHRwDQ/2gYpp4BeYeHoo7OYXn4Ndg/view?utm_content=DAFlIyHRwDQ&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)

## Circuit Diagrams

### Receiver Circuit Diagram

<img width="1175" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/71113b25-8084-4cd8-875c-f3264c376764">


### Transmitter Circuit

<img width="1175" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/aade8ce1-b995-46ad-a1e8-2d233911103d">


## PINOUT Schematics
<img width="639" alt="image" src="https://github.com/iremkrc/handi-wheel/assets/66200657/3bd7e100-66b0-43c7-aae7-da8e4ef8f147">
