# Embedded 3-Phase Monitoring System

A real-time embedded monitoring platform for 3-phase electrical systems using the STM32H743 microcontroller.

This project focuses on high-speed electrical signal acquisition, real-time signal processing, and web-based monitoring for research and industrial applications.

The repository was developed for academic research and journal publication purposes related to embedded power monitoring systems.
---

## Features

- 3-phase voltage monitoring
- 3-phase current monitoring
- High-speed ADC sampling
- Real-time web monitoring GUI
- Modular firmware architecture
- Expandable communication interface

---

## Hardware Components

### Microcontroller

STM32H743 high-performance ARM Cortex-M7 microcontroller.
The STM32H743 provides:
- Triple ADC peripherals
- High processing performance
- Fast timer synchronization
- Real-time signal processing capability
- Large memory resources

![STM32H743](photo/stm32h743.png)

---

### Voltage Sensor

Voltage sensing circuit for 3-phase AC measurement. Single-ended analog input is used for AC voltage sensing.

![Voltage Sensor](photo/voltage_sensor.png)

---

### Current Sensor

Current sensing module using CT/Hall-effect sensor. Differential analog input is used for AC current sensing to improve noise immunity and measurement accuracy.

![Current Sensor](photo/current_sensor.png)

---

## System Architecture

The following diagram shows the overall system architecture.

![Architecture](photo/architecture_.png)

---
# Data Acquisition Architecture

The monitoring system utilizes the triple ADC architecture available in the STM32H743.

## Multi-ADC Configuration

Each ADC is assigned to one electrical phase:

- ADC1 → Phase A
- ADC2 → Phase B
- ADC3 → Phase C

This configuration allows simultaneous acquisition of all 3 phases with minimal timing offset. All ADCs are synchronously triggered using a hardware timer operating at: 20 kHz

---
## Web Monitoring Interface

Real-time monitoring dashboard for displaying electrical parameters.

Features:
- Voltage monitoring
- Current monitoring
- Frequency display
- Live sensor updates

![Web GUI](photo/web_gui.png)

---

## Software Architecture

```text
ADC Sampling
    ↓
Signal Conditioning
    ↓
Communication Layer
    ↓
Web Monitoring GUI
