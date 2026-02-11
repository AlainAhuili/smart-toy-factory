Smart Toy Factory

An interconnected network of wooden toy vehicles and machinery communicating via CAN Bus, bridging virtual programming with real-world action.
🚀 The Hybrid Experience

This project moves beyond simulation. Kids write code in a virtual environment (Python) that directly controls physical, motorized wooden toys.

    Virtual Goal: Manage a digital factory on screen.

    Physical Action: Python scripts command real machinery to move physical blocks and real cars to transport them.

    Real-time Feedback: Sensors on the toys feed data back to the virtual game.

Repository Structure

    docs/: Schematics, datasheets, and design notes.

    gateway/: Firmware for the bridge node (USB to CAN).

    nodes/: Firmware for individual vehicle and machinery microcontrollers.

    programming_ui/: Scripts for high-level control.

Setup Requirements
Hardware

    Microcontrollers (e.g., ESP32, STM32)

    CAN Transceivers (e.g., SN65HVD230)

    Motors and Servos for toys

    Twisted pair wiring for the CAN bus

Software

    PlatformIO or Arduino IDE for C/C++ firmware

    Python 3 for the interface gateway

🧠 CAN Bus Protocol Strategy

To ensure seamless interaction between all toys, we use a structured 11-bit CAN ID system.
🎮 How to Run the Hybrid Game
1. Setup Physical Hardware

Connect the CAN transceivers to your microcontrollers and connect all nodes together using twisted pair wiring. Connect the Gateway node to your computer via USB.
2. Flash Firmware

Upload the code from /gateway and /nodes to your respective microcontrollers.
3. Run the Virtual Controller

Navigate to /programming_ui and run the simulation script:

Kids can now use Python commands like move_crane(position) to manipulate the real toys!

CAN Message ID Allocation Strategy

We will use the ID to indicate Priority, Device Type, and Instance.
Priority Mapping

    0-1: Safety Critical (e.g., Emergency Stop, Collision Detect)

    2-4: Movement Control (e.g., Throttle, Steering)

    5-7: Monitoring/Status (e.g., Battery level, Position feedback)

Example Message Table
Data Payload Structure

For movement messages, use a simple 2-byte or 4-byte payload:

    Byte 0: Command Type (e.g., 0x01 = Set Speed, 0x02 = Set Steering)

    Byte 1: Value (e.g., 0-100 or -127 to 127)
