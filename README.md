# Automated Waste Segregation System (IoT & Embedded Systems)

An automated "at-source" domestic waste sorter engineered to classify refuse into **Metallic, Wet, and Dry** categories. This project leverages an Arduino Uno and a multi-sensor array to improve recycling efficiency and reduce human error in waste management.

---

## Technical Stack
* **Microcontroller:** Arduino Uno (Atmega328P)
* **Sensor Suite:** * Inductive Proximity Sensor (Inductance-based metal detection)
    * Infrared (IR) Sensor (Object presence & proximity)
    * Moisture/Raindrop Sensor (Conductivity-based wet waste detection)
* **Actuators:**
    * 28BYJ-48 Stepper Motor (Precision platform positioning)
    * MG90S Servo Motor (Dispensing mechanism)
    * Active Buzzer (Auditory status alerts)
* **Libraries:** `CheapStepper.h`, `Servo.h`

---

## Circuit Documentation
The following diagram illustrates the sensor-actuator interfacing and pin configuration used for this prototype.

![Circuit Diagram](Automated_Waste_Segregator_circuit_diagram.png)

---

## System Logic & Workflow
The firmware implements a sequential analysis algorithm to ensure high classification accuracy:

1.  **Detection Phase:** The system remains in an idle state until the **IR Sensor** detects an incoming object.
2.  **Analysis Phase:**
    * **Inductive Test:** If the **Proximity Sensor** triggers, the object is flagged as **Metallic**. The platform rotates **240° CCW**.
    * **Moisture Mapping:** If no metal is detected, the system pulls 3 sequential analog readings from the **Moisture Sensor**. If the averaged value exceeds a **20% threshold**, it is flagged as **Wet**. The platform rotates **240° CW**.
    * **Default State:** Objects not meeting the above criteria are classified as **Dry**.
3.  **Action Phase:** Once aligned, the **Servo Motor** actuates the lid, and the **Buzzer** confirms the transaction before the platform resets to the home position.

---

## ♻️ Sustainability & Design
Guided by the **3Rs Principle (Reduce, Reuse, Recycle)**, the physical chassis was constructed using repurposed PVC conduits, plywood remnants, and recycled plastic containers, ensuring a cost-effective and eco-friendly prototype development.
