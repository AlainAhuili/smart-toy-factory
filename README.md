Smart Toy Factory

An interconnected network of toy vehicles and wooden machinery communicating via CAN Bus, controlled through a user-friendly interface.
Project Overview

This project bridges physical engineering with software programming by creating a modular, robust automation system based on real-world automotive standards.

    Communication Protocol: CAN Bus (Controller Area Network)

    Vehicles: Remote-controlled wooden cars/trucks.

    Machinery: Custom wooden machinery (conveyor belts, robotic arms).

    Control Interface: Python / Scratch bridge for educational accessibility.

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
