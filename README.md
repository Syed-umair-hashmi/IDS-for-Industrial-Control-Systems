# ICS Anomaly Detection

## Overview

This project implements a machine learning–based anomaly detection system for Industrial Control Systems (ICS). The goal is to model normal system behavior and detect deviations that may indicate cyberattacks or abnormal process activity.

Industrial Control Systems operate critical infrastructure such as water treatment plants, power grids, and manufacturing facilities. Because these systems typically follow predictable and deterministic patterns, abnormal behavior can often indicate system faults, sensor manipulation, or malicious activity.

To address this, the model is trained on normal ICS operational data to learn how the system typically behaves. Incoming observations are then compared against this learned baseline to determine whether they represent normal operation or a potential anomaly.
We will use normal ICS Data to teach a model how a system usually behaves. We will then monitor new data for any system inconsistencies and if the new behavior differs enough from the learned normal pattern, we would mark it as anomalous or potentially malicious for safety concerns.

## Detection Approach

The system follows an anomaly detection pipeline:

1. Train on normal data:
The model learns the baseline behavior of the ICS environment using normal operational data.
2. Feed in new observations:
New system observations are collected from later operational periods or datasets that may contain attacks.
3. Measure deviation from normal behavior: 
The model evaluates how different the new observations are compared to the learned normal patterns.
4. Generate a detection result:
If the deviation exceeds a defined threshold, the observation is flagged as an anomaly or potentially malicious activity.

## Pipeline Architecture

```
Normal ICS Data
      │
      ▼
Preprocessing & Feature Extraction
      │
      ▼
Train Anomaly Detection Model
      │
      ▼
Incoming ICS Observations
      │
      ▼
Deviation Score Calculation
      │
      ▼
Normal / Anomaly Classification
```

## Key Concept

The model learns the relationships between sensors, actuators, and system states over time. By modeling these normal relationships, the system can identify inconsistencies such as abnormal sensor readings, unexpected actuator behavior, or unusual process dynamics that may indicate faults or cyberattacks.
