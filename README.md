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
