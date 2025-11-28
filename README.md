# ⚙️ Design and Simulation of a 1 HP, 1500 RPM, 3-Phase Synchronous Machine

This folder contains my ECEN 436 final project at the University of Nebraska–Lincoln, where I designed and analyzed a 6-pole, 1 hp, 1500 rpm three-phase synchronous machine using ANSYS Maxwell 2D.

## 📌 Course

- Course: ECEN 436 – Electric Machines  
- University: University of Nebraska–Lincoln (UNL)  
- Instructor: Dr. Liyan Qu  
- Student: Phelopater Ramsis  

## 🧾 Project Overview

The goal of this project was to build and test, in simulation, a 6-pole, 1500 rpm, 1 hp three-phase synchronous machine with:

- Target torque around 4.75 N·m  
- High efficiency  
- Reasonable material cost  

All electromagnetic modelling was done in ANSYS Electronics Desktop (Maxwell 2D).  
The report walks through several design phases where I iterated on geometry, material selection, and loading to balance cost and performance.

## 🛠️ Machine Design

Main machine characteristics:

- Type: 3-phase synchronous machine  
- Number of poles: 6  
- Stator slots: 18  
  - Slot width: 10 degrees electrical  
  - Slot depth: 15 mm  
- Rotor: 6 NdFeB permanent magnets (grade N35)  
  - Each magnet covers 40 degrees  
  - Magnet thickness: 4 mm  
- Machine outer diameter: 100 mm  
- Axial length: 100 mm  
- Copper fill factor: about 35% of the slot area  

Material data used in the design:

- Copper cost: 4.40 USD / kg  
- Steel cost: 1.50 USD / kg  
- NdFeB magnet cost: 240 USD / kg  
- Copper resistivity: 1.72e-8 ohm·m  
- Copper density: 8900 kg/m³  
- Steel density: 7800 kg/m³  
- NdFeB density: 7400 kg/m³  

## 📐 Methods

### 1️⃣ Electromagnetic Modelling in ANSYS

- Built the 2D cross-section of stator, slots, rotor and magnets.  
- Assigned materials (electrical steel, copper, NdFeB).  
- Defined the winding layout and current excitation.  
- Ran finite-element simulations to obtain torque, flux distribution and losses.  

### 2️⃣ Copper Volume and Winding Calculations

For each phase:

- Estimated end-turn length using an average radius inside the stator  
  (inner stator radius plus half the slot depth).  
- Calculated the copper cross-section per slot from slot volume and fill factor.  
- Computed copper volume per phase as:  
  copper volume = cross-section area × (slot length + end-turn length).  
- Total copper volume = 3 × volume of one phase.  

### 3️⃣ Cost Calculation

- Used ANSYS volume tools to extract volumes of steel, magnets and copper.  
- Converted volume to mass using the material densities.  
- Cost of each material = mass × cost per kg.  
- Total active material cost = sum of all material costs.  

### 4️⃣ Losses and Efficiency

- Calculated copper resistance per phase from resistivity, length and area.  
- Copper losses:  
  P_copper = 3 × (I_rms^2) × R.  
- Core losses: taken from specific loss curves vs. peak flux density in the steel.  
- Overall efficiency:  
  efficiency = P_out / (P_out + P_copper + P_core).  

A spreadsheet was used to collect all formulas and parameters in one place so I could quickly change geometry, loading and flux levels and immediately see the impact on cost, losses and efficiency.

## 📊 Results and Discussion

- The final design meets the torque target of roughly 4.75 N·m at 1500 rpm.  
- Material usage and cost were evaluated for copper, steel and magnets.  
- Copper and core losses were quantified and used to estimate overall efficiency.  
- Several iterations were performed to improve efficiency without making the machine too large or too expensive.

The combination of ANSYS simulations and spreadsheet calculations made it possible to explore trade-offs between:

- Torque capability  
- Efficiency  
- Active material volume  
- Total cost  

## 🎓 Benefits and Learning Outcomes

From this project I gained:

- Hands-on experience using ANSYS Maxwell for electric machine design.  
- A stronger understanding of how geometry, materials and loading affect torque, losses and efficiency.  
- Insight into cost vs. performance trade-offs for copper, steel and magnets.  
- A practical workflow for prototyping machines in simulation before building any hardware, saving both time and money.  

## 🗂️ Files in This Folder

- `EM Project.pdf` – full course project report with figures, equations and detailed results.  
- `README.md` – this summary file.  
