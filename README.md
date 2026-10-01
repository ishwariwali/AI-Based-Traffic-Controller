
# Adaptive Multi-Junction Traffic Grid Controller (AMTGC)

## 📌 Project Overview
The **Adaptive Multi-Junction Traffic Grid Controller (AMTGC)** is a robust, scalable traffic management system designed using **Verilog HDL**. It transitions from theoretical finite state machine (FSM) concepts to industry-standard RTL design and verification. The system optimizes real-world traffic congestion by dynamically adjusting green light durations based on real-time traffic density.

## 🚀 Key Features
* **Adaptive Timing:** Dynamically calculates target green times (Target = Min Time + Density × 2) rather than using static timers.
* **Master-Slave Green-Wave Synchronization:** Coordinates Junction A (Master) and Junction B (Slave) for seamless vehicle flow across the grid.
* **Emergency Override:** Strictly prioritized asynchronous logic that instantly forces an "All-Red" safe state during emergencies.
* **Fair Pedestrian Arbiter:** A round-robin request system that grants crossing phases without causing starvation for pedestrians.
* **Automated Verification:** A self-checking testbench architecture in ModelSim that verifies 100+ randomized operational scenarios and extreme corner cases.

## 📁 Repository Structure
* `/rtl` : Contains the main Verilog source files (Top-level, Junction Controller, Generic Timer).
* `/tb` : Contains the automated self-checking testbench files.
* `/docs` : Contains the Technical Report (PDF) and Architectural Diagrams.

## 🛠️ Tools Used
* **Hardware Description Language:** Verilog HDL
* **Simulation & Verification:** Siemens ModelSim
* **Design Methodology:** FSM-based RTL Design

## 💻 How to Run the Simulation
To verify the design using ModelSim, follow these steps:
1. Compile all the `.v` files from the `/rtl` and `/tb` folders.
2. Load the simulation by entering the following command in the transcript:
   `vsim work.tb_amtgc_top_selfcheck`
3. Run the automated tests by typing:
   `run -all`
4. The transcript will display **"ALL TESTS PASSED"** upon successful verification.

## 📄 Documentation
For detailed architectural decisions, state diagrams, and bug resolution logs, please refer to the `AMTGC_Technical_Report.pdf` located in the `/docs` folder.
