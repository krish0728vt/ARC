
# ARC — Autonomous Robotic Companion

> **Project Status:** Concept design and engineering planning in progress. Hardware, drivetrain, PCB, and AI performance are not yet validated.

![ARC Robot Concept](hero(1).png)

## Project Owner

**Name:** Krish Shah  
**Virginia Tech Email:** krish0728@vt.edu

## Project Overview

**ARC (Autonomous Robotic Companion)** is a compact, AI-powered mobile robot designed to see, listen, speak, express emotions, and move around its environment. The goal of this project is to develop an interactive robotic companion by combining embedded systems, mechanical design, electronics, robotics, and locally hosted artificial intelligence.

ARC will feature a fully 3D-printed, cube-shaped body approximately **10–12 cm tall**, with a backward-sloping front face. A **full-color display** will show animated eyes and facial expressions, allowing the robot to communicate emotions and respond visually during conversations. A small, fixed camera mounted above the body will provide visual input, while **two independently controlled continuous tank tracks** will enable movement and turning.

The robot will use a **Seeed Studio XIAO ESP32-S3 Sense** microcontroller to manage its onboard hardware, including the camera, microphone, display, speaker, Wi-Fi connectivity, and motor controls.

More demanding AI processing will be performed on an **external Raspberry Pi 3 Model B+**, connected wirelessly over Wi-Fi. The Raspberry Pi will handle lightweight speech recognition, language processing, and speech generation. A separate computer may optionally provide additional processing power when available.

A major objective is to develop the system using **free, open-source, locally hosted AI software**, without requiring paid cloud services or third-party AI API keys.

The final goal is to create a functional, rechargeable, and interactive robot with expressive animations, conversational capabilities, visual awareness, and safe autonomous or remotely controlled movement.

## What I Hope to Learn

Through this project, I hope to gain practical experience in several areas of electrical engineering, computer engineering, and robotics.

### 1. Embedded Systems and Firmware Development
- Programming and configuring the ESP32-S3 microcontroller.
- Integrating cameras, microphones, speakers, and displays.
- Developing firmware for real-time hardware control.
- Implementing communication between embedded devices.

### 2. PCB and Electronics Design
- Designing custom printed circuit boards using electronic design software.
- Integrating motor drivers, power management, charging circuits, and sensors.
- Understanding battery protection, voltage regulation, and power distribution.
- Testing and debugging electronic circuits.

### 3. Mechanical Design and 3D Printing
- Developing parametric CAD models for robotic systems.
- Designing compact enclosures and mechanical assemblies.
- Creating functional tank tracks, sprockets, and motor mounts.
- Understanding tolerances, material selection, and mechanical constraints.

### 4. Robotics and Motion Control
- Implementing differential-drive locomotion.
- Controlling DC gearmotors through motor driver circuits.
- Developing safe motion-control algorithms.
- Understanding mechanical load, torque, traction, and motor efficiency.

### 5. Artificial Intelligence and Networking
- Integrating locally hosted speech recognition and text-to-speech systems.
- Exploring lightweight language models.
- Connecting embedded hardware to an external AI server over Wi-Fi.
- Developing interactive voice-controlled robotic behaviors.
- Understanding the hardware limitations of running AI models locally.

### 6. System Integration and Testing
- Combining mechanical, electrical, and software subsystems.
- Troubleshooting hardware and software compatibility issues.
- Evaluating power consumption, response time, and reliability.
- Improving the design through prototyping and engineering validation.

## Design and Implementation

ARC is currently in the preliminary engineering design stage. The following sections describe the planned system architecture and components.

### 1. Mechanical Design

The robot will have a compact, fully 3D-printed body with a futuristic appearance inspired by small AI companion robots.

**Main design features:**

- Approximately 100–120 mm overall height.
- Cube-like enclosure with a backward-sloping front face.
- Full-color animated display integrated into the front.
- Small fixed camera module positioned above the body.
- Two continuous tank tracks mounted along the sides.
- Independently driven left and right tracks.
- Removable rear panel for electronics access.
- Internal mounting structures for the battery, PCB, and motors.
- Compact and organized wiring.

The preliminary design has been created using **OpenSCAD** under the earlier engineering codename CUBE-01.

The existing CAD model represents the initial mechanical layout and component packaging. The drivetrain, mounting arrangements, and manufacturing tolerances still require further development and testing.

### 2. Electrical and Hardware Design

The main onboard controller will be the **Seeed XIAO ESP32-S3 Sense**, selected for its compact size, Wi-Fi capabilities, integrated microphone, and camera support.

**Proposed hardware components:**

| Component | Purpose |
|---|---|
| XIAO ESP32-S3 Sense | Main onboard microcontroller |
| Waveshare 2-inch ST7789 LCD | Animated eyes and facial expressions |
| Integrated camera module | Image capture and visual input |
| Integrated microphone | Voice input |
| MAX98357A amplifier | Digital audio output |
| Miniature speaker | Voice responses and sound effects |
| Two N20 DC gearmotors | Left and right track movement |
| Motor driver circuits | Independent motor speed and direction control |
| Rechargeable LiPo battery | Portable power supply |
| Battery charging circuit | Safe battery charging |
| Battery fuel gauge | Battery monitoring |
| Custom PCB | Integrated electrical connections and power distribution |

The final motor drivers, battery, and power-management components will be selected after electrical measurements and component testing.

A custom PCB will eventually replace temporary prototype wiring to create a compact, reliable, and serviceable system.

### 3. Display and Facial Animation

One of ARC's primary features will be its animated face.

The robot will use a full-color LCD mounted on its sloped front surface.

Planned facial expressions include:

- Idle and blinking
- Listening
- Thinking
- Speaking
- Happy
- Curious
- Confused
- Sleeping
- Low battery
- Disconnected

The animation system will be developed using concepts and reusable components from the open-source **Face for Xiaozhi** project.

### 4. Camera and Computer Vision

ARC will feature a small, fixed camera mounted above its main body.

The camera will be angled slightly upward to observe its surroundings.

Planned capabilities include:

- Capturing images.
- Sending images over Wi-Fi.
- Processing visual information through an external computer.
- Answering questions about objects or surroundings when compatible vision AI is available.

Advanced computer vision will initially depend on external processing hardware.

### 5. Tank Track Locomotion

ARC will move using two continuous tank tracks.

Each track will be independently controlled by a miniature DC gearmotor, enabling:

- Forward movement
- Reverse movement
- Left and right turns
- Pivot turns
- Variable-speed movement

The track mechanism will be designed for 3D printing, with potential use of flexible TPU tracks and rigid printed sprockets.

The final mechanism will require testing to determine suitable motor torque, track tension, traction, and mechanical durability.

### 6. Software and AI Architecture

ARC will use a distributed processing system.

**Onboard ESP32-S3:**

- Hardware control
- Display animations
- Microphone and speaker interfaces
- Camera capture
- Motor control
- Wi-Fi communication
- Basic safety functions

**External Raspberry Pi 3B+:**

- Local speech recognition
- Lightweight language-model processing
- Text-to-speech generation
- Conversation management
- Communication with the robot

**Optional external PC:**

- More capable language models
- Advanced speech processing
- Image understanding
- Additional AI computation

The Raspberry Pi will remain external to the robot and communicate over Wi-Fi.

The software will be based on open-source projects, including:

- Xiaozhi ESP32
- Face for Xiaozhi
- ESP-IDF
- llama.cpp
- Vosk
- eSpeak NG

The goal is to provide local AI functionality without requiring paid cloud APIs.

Due to the Raspberry Pi 3B+'s limited 1 GB RAM, AI performance and response times will need to be evaluated experimentally.

### 7. Testing and Validation

Development will be divided into smaller hardware and software tests before complete integration.

Planned testing includes:

- LCD display initialization and animation.
- Microphone audio capture.
- Speaker audio playback.
- Camera image capture.
- ESP32 Wi-Fi communication.
- Raspberry Pi AI processing.
- Motor driver functionality.
- Track movement and traction.
- Battery charging and power consumption.
- Complete voice interaction.
- Integrated system reliability.

Final PCB fabrication and full mechanical assembly will follow successful subsystem validation.

## Bill of Materials

The following table contains the preliminary components planned for the project. Exact quantities, component models, and prices may change as development progresses.

| Item | Quantity | Estimated Cost | Link |
|---|---:|---:|---|
| Seeed XIAO ESP32-S3 Sense | 1 | TBD | [Seeed Studio](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/) |
| Waveshare 2-inch ST7789 Color LCD | 1 | TBD | [Waveshare](https://www.waveshare.com/product/2inch-lcd-module.htm) |
| N20 DC Gearmotors | 2 | TBD | TBD |
| DRV8830 Motor Drivers (provisional) | 2 | TBD | [Texas Instruments](https://www.ti.com/product/DRV8830) |
| MAX98357A Audio Amplifier | 1 | TBD | [Analog Devices](https://www.analog.com/en/products/max98357a.html) |
| Miniature Speaker | 1 | TBD | TBD |
| Rechargeable Protected LiPo Battery | 1 | TBD | TBD |
| Battery Charging Circuit | 1 | TBD | [BQ24074](https://www.ti.com/product/BQ24074) |
| Battery Fuel Gauge | 1 | TBD | [MAX17048](https://www.analog.com/en/products/max17048.html) |
| Custom PCB | 1 | TBD | TBD |
| Connectors, Switches, and Fasteners | As needed | TBD | TBD |
| PLA/PETG/TPU 3D Printing Filament | As needed | TBD | TBD |
| Raspberry Pi 3 Model B+ | 1 | Already Owned | [Raspberry Pi](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/) |

**Estimated Total Cost:** TBD

The total estimated project cost will be updated after final component selection and supplier pricing.

## Timeline and Milestones

| Milestone | Target Date | Status |
|---|---|---|
| Project planning and research | October 2026 | In Progress |
| Preliminary mechanical and electrical design | October–November 2026 | In Progress |
| ESP32 display and audio prototype | TBD | Not Started |
| Camera and Wi-Fi integration | TBD | Not Started |
| Raspberry Pi AI server development | TBD | Not Started |
| Motor control and track development | TBD | Not Started |
| Battery and power-system testing | TBD | Not Started |
| Custom PCB design and fabrication | TBD | Not Started |
| Full robot assembly | TBD | Not Started |
| Final integration and testing | TBD | Not Started |
| Project completion | TBD | Not Started |

## Progress Log

### 2026-10-28 — Initial Project Planning

**Completed:**

- Defined the initial concept and objectives of the AI companion robot.
- Selected the project name **ARC — Autonomous Robotic Companion**.
- Established the approximate robot size and physical design.
- Selected a cube-like body with a backward-sloping front surface.
- Chose a full-color animated display for facial expressions.
- Selected a small, fixed camera configuration.
- Decided to use continuous tank tracks for movement.
- Identified the XIAO ESP32-S3 Sense as the main onboard controller.
- Selected the existing Raspberry Pi 3B+ as the external AI processing device.
- Established the goal of locally hosted, open-source AI.
- Developed preliminary 3D CAD concepts and internal component layouts.
- Identified the main electrical, mechanical, and software design challenges.

**Next Steps:**

- Verify hardware compatibility and component dimensions.
- Begin ESP32-S3 and color-display prototyping.
- Test microphone, speaker, and camera functionality.
- Develop and evaluate the local Raspberry Pi AI architecture.
- Continue refining the mechanical design.

## Project Files

The repository will contain all major project files as development progresses.

**Planned repository organization:**

```text
ARC/
├── README.md
├── hero.png
│
├── cad/
│   ├── models/
│   ├── printable-parts/
│   └── assembly/
│
├── hardware/
│   ├── schematics/
│   ├── pcb/
│   ├── datasheets/
│   └── bom/
│
├── firmware/
│   ├── esp32/
│   ├── display/
│   ├── audio/
│   └── motor-control/
│
├── server/
│   ├── raspberry-pi/
│   ├── speech/
│   └── ai/
│
└── docs/
    ├── design-notes/
    ├── testing/
    └── progress/
```

The directory structure will be created and updated as the project develops.

## Useful Links

### Hardware Documentation

- [Seeed XIAO ESP32-S3 Documentation](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/)
- [Waveshare 2-inch LCD Documentation](https://www.waveshare.com/wiki/2inch_LCD_Module)
- [DRV8830 Motor Driver](https://www.ti.com/product/DRV8830)
- [BQ24074 Battery Charger](https://www.ti.com/product/BQ24074)
- [MAX17048 Fuel Gauge](https://www.analog.com/en/products/max17048.html)

### Firmware and Software

- [Xiaozhi ESP32 Firmware](https://github.com/78/xiaozhi-esp32)
- [Face for Xiaozhi](https://github.com/TechTalkies/Face-for-Xiaozhi)
- [ESP-IDF](https://github.com/espressif/esp-idf)
- [llama.cpp](https://github.com/ggml-org/llama.cpp)
- [Vosk Speech Recognition](https://alphacephei.com/vosk/)
- [eSpeak NG](https://github.com/espeak-ng/espeak-ng)

## Project Image

![ARC — Autonomous Robotic Companion](hero.png)

The current image represents the preliminary design concept of ARC.

The image will be updated as the physical robot is developed and assembled.

The project cover image is stored as `hero.png` in the root directory so that it can be displayed on the AMP Lab project website.

---

**ARC — Autonomous Robotic Companion**

*An open-source robotics project exploring embedded systems, intelligent interaction, mechanical design, and locally hosted AI.*
