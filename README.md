# Project Overview: Simulation of a Car's Functionality Using the Arduino Platform

## 1. What does the project do?  
My project consists of creating an interactive system that simulates the basic components and functionality of a car using an Arduino platform. It includes the following components and features:

- **Buttons**: Control the brake, clutch, and acceleration, simulating speed control and stopping.  
- **Joystick**: Used as a gear shift lever to simulate transmission levels.  
- **LCD Screen**: Acts as a virtual dashboard, displaying information such as:  
  - Current speed  
  - Total mileage  
  - Gear shift position  
  - Other essential data.  

---

## 2. Project Purpose  
The main purpose of this project is to develop an educational platform that facilitates the understanding of the basic principles behind the functionality of a modern vehicle. It provides the opportunity to explore concepts in electronics, programming, and automation in a practical and hands-on way.  

The project aims to:  
- Help users understand the interaction between hardware and software components.  
- Develop practical skills in designing and implementing integrated systems.  
- Demonstrate how sensors and electronic components can be used to simulate a complex system like a car.  

---

## 3. Inspiration for the Project  
I started with the idea of combining learning with practical applicability, drawing inspiration from the complexity of modern automotive systems. I wanted to create an accessible and educational model that reflects, on a smaller scale, the basic functionality of a car.  

The main goal was to put into practice the knowledge I gained in microcontrollers and offer an interactive experience to users.  

---

## 4. Why do I believe it is useful?  

### For the community and peers:  
- This project provides an innovative and educational approach to electronic and mechanical systems, useful for both students and technology enthusiasts.  
- It serves as an example of how theoretical concepts can be integrated into a functional project.  
- It can be used as educational material or as inspiration for similar projects.  

### For me:  
- It allows me to deepen my knowledge of Arduino, sensors, and electronic displays.  
- It helps me develop problem-solving, programming, and hardware design skills.  
- It represents an opportunity to learn how to plan and implement a complex project.  

---

## 5. Possible Future Extensions  
The project can be further developed by:  
- Adding additional sensors (e.g., to simulate fuel consumption or collision detection).  
- Integrating a Bluetooth or Wi-Fi module for vehicle monitoring and control via a mobile app.  
- Creating a more advanced virtual environment, including maps or a road simulator.  

---


## **Current Hardware Implementation**

The system includes the following components:
- Four DC motors controlled by two L293D motor driver modules.
- An HC-05 Bluetooth module for wireless control.
- An LCD display for real-time speed feedback.
- LEDs representing taillights.
- Buttons for acceleration, braking, clutch, and activating taillights.
- A joystick simulating a gear shift.

---

## **Block Diagram**

```plaintext
[Bluetooth Module] --> [Arduino Uno] --> [L293D Modules] --> [Motors]
                               |             |
                            [LCD]         [LEDs]
                               |             |
                            [Buttons]   [Joystick]
```
(Add an image showing the connections between all components for better clarity.)

---

## **Electrical Schematic**

(Attach or link to the full schematic diagram illustrating wiring for Arduino, L293D modules, motors, LCD, buttons, joystick, and LEDs.)

---

## **Bill of Materials (BOM)**

| **Component**         | **Quantity** | **Description**                     | **Source/Link**                                                                                 | **Datasheet**                                                                 |
|------------------------|--------------|-------------------------------------|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| Arduino Uno            | 1            | Microcontroller for control         | [University Of Bucharest]                              | [Datasheet]([https://store.arduino.cc/uno-rev3](https://octopart.com/datasheet/arduino+uno+wifi+rev2-arduino-116872670?msclkid=0b31ffc1053c1595b00098a1493dae37&utm_source=bing&utm_medium=cpc&utm_campaign=b_cpc_emea-ro_search_dsa_english_en_usd_all-categories&utm_term=semiconductors&utm_content=Discrete%20Semiconductors%20DSA))                               |
| L293D Motor Driver     | 2            | Controls the DC motors              | [University Of Bucharest]                      | [L293D Datasheet]([https://www.ti.com/lit/ds/symlink/l293d.pdf](https://www.alldatasheet.com/view.jsp?Searchword=L2930))               |
| DC Motors              | 4            | Provides car movement               | [University Of Bucharest]                                  | [DC Motor Datasheet](https://components101.com/motors/dc-motor)             |
| HC-05 Bluetooth Module | 1            | Enables Bluetooth communication     | [HC-05 Module](https://www.optimusdigital.ro/en/wireless-bluetooth/153-hc-05-master-slave-bluetooth-module-with-adapter-33v-and-5v-compatible.html)                                       | [HC-05 Datasheet](https://components101.com/wireless/hc-05-bluetooth-module)|
| 16x2 LCD Display       | 1            | Displays speed and status           | [University Of Bucharest]                                             | [LCD Datasheet](https://components101.com/displays/16x2-lcd-display-module) |
| Potentiometer          | 1            | Adjusts LCD contrast                | [University Of Bucharest]                              | N/A                                                                           |
| LEDs                   | 2            | Represents taillights               | [University Of Bucharest]                                       | [LED Datasheet](https://components101.com/leds/5mm-led-datasheet)           |
| Joystick Module        | 1            | Acts as a gear shifter              | [University Of Bucharest]                                      | [Joystick Datasheet](https://components101.com/switches/joystick-module)    |
| Buttons                | 4            | For acceleration, braking, clutch   | [University Of Bucharest]                                     | N/A                                                                           |
| Breadboard             | 1            | Simplifies connections              | [University Of Bucharest]                                         | N/A                                                                           |
| Resistors (220Ω)       | 2            | For LED protection                  | [University Of Bucharest]                                   | N/A                                                                           |

---

## **Pin Configuration**

| **Component**        | **Pins Used**              | **Description**                                     |
|-----------------------|----------------------------|---------------------------------------------------|
| Motor 1              | 3, 4, 5                    | Direction and speed control (via PWM).            |
| Motor 2              | 6, 7, 8                    | Direction and speed control (via PWM).            |
| Motor 3              | 9, 10, 11                  | Direction and speed control (via PWM).            |
| Motor 4              | 12, 13, 2                  | Direction and speed control (via PWM).            |
| HC-05 Bluetooth      | 0 (RX), 1 (TX)             | Serial communication for wireless control.        |
| LCD                  | 12, 11, 5, 4, 3, 2         | Display speed and status.                         |
| LEDs (Taillights)    | Digital Pins (customizable)| Visual indicators controlled by a button.         |
| Buttons              | Digital Pins (customizable)| Used for manual controls (e.g., brake, clutch).   |
| Joystick             | Analog Pins (A0, A1)       | Gear shifting input.                              |

---

## **Functional Description**

- **Motors**: Four DC motors are controlled using two L293D drivers.
  - Motor 1: Pins 3, 4, 5.
  - Motor 2: Pins 6, 7, 8.
  - Motor 3: Pins 9, 10, 11.
  - Motor 4: Pins 12, 13, 2.
- **Bluetooth Module (HC-05)**: Enables wireless control of the car through a smartphone or other devices.
- **LCD**: Displays real-time speed and status of the car.
- **Buttons**:
  - Acceleration: Increases motor speed via PWM.
  - Brake: Stops the car by setting motor pins LOW.
  - Clutch: Enables gear shift using the joystick.
  - Taillight Button: Toggles LED taillights.
- **Joystick**: Simulates a gear shift by mapping analog input to gear ratios.

---

## **Proof of Functionality**

- Include pictures of:
  - The breadboard with components connected.
  - The LCD displaying speed data.
  - LEDs lighting up when the taillight button is pressed.
- Add video evidence of the car moving and the controls functioning.

---

## **Project Milestones**

1. Initial motor control implementation and testing.
2. Bluetooth communication established and verified.
3. LCD displays speed data correctly.
4. Taillight LEDs toggle via button press.
5. Joystick integrated for gear shifting.
6. Complete system functionality tested and verified.

---

## **Contributions**
Contributions are welcome! Feel free to open issues or submit pull requests to enhance the project.


My project aims to offer a combination of technology and education, contributing to a better understanding of the interactions between hardware and software components in a complex system.
