# Safety Evaluation of a Printed Circuit Board (PCB) During Drop Impact  

## Project Description  
This project investigates the behavior of a **Printed Circuit Board (PCB)** during a drop impact from a height of 1 meter, analyzing its safety when enclosed in protective packaging made from either **foam** or **elastomer**. The aim was to determine whether the packaging materials provide sufficient protection to prevent damage to the PCB, which is highly sensitive to mechanical impacts.  

The analysis simulates realistic conditions, such as accidental drops during transportation or typical handling in warehouses, providing valuable insights into the effectiveness of different protective materials.  

---

## Execution Details  

### 1. Model Setup  
The model consists of three components:  
- **Floor**: A rigid planar shell representing the impact surface.  
- **Protective Packaging**: Made from either foam or elastomer, modeled as deformable solids.  
- **PCB**: A composite shell with three reference points to represent chips mounted on the board.  

The assembly simulates the PCB positioned inside the protective packaging and falling at a specific angle determined by auxiliary planes and axes.

### 2. Material Properties  

#### PCB Material (Composite):  
- **Young’s Modulus**: \( 4.5 \times 10^{10} \, \text{Pa} \)  
- **Density**: \( 1500 \, \text{kg/m}^3 \)  
- **Poisson’s Ratio**: 0.3  

#### Foam:  
- **Young’s Modulus**: \( 3.0 \times 10^{6} \, \text{Pa} \)  
- **Density**: \( 100 \, \text{kg/m}^3 \)  
- **Poisson’s Ratio**: 0.0  
- Modeled as **Crushable Foam** with volumetric hardening to simulate compressive stress-strain behavior.  

#### Elastomer:  
- **Density**: \( 1500 \, \text{kg/m}^3 \)  
- Modeled as a **Hyperelastic material** using the Ogden strain energy potential with experimental data from uniaxial tensile tests.

### 3. Mesh  
- **PCB**: 100 elements (S4R).  
- **Packaging**: 630 elements (C3D8R).  
- **Floor**: Single element (R3D4).  
Mesh refinement includes **Hourglass Control** for stability and accuracy.  

### 4. Simulation Settings  
- **Step Type**: Dynamic, Explicit.  
- **Time Step**: 0.02 seconds for simulating free fall from 1 meter.  
- **Initial Conditions**:  
  - Initial velocity calculated as \( v = \sqrt{2 \cdot g \cdot h} \approx 4.43 \, \text{m/s} \).  
  - Gravity applied along the Z-axis.  
- **Contact**: General contact algorithm with a friction coefficient of 0.3.  

---

## Observations and Analysis  

### Variant 1: Foam Packaging  
- **Acceleration**: Peak acceleration values reached **2300 m/s²**, remaining within IPC safety standards.  
- **Velocity**: Smooth deceleration indicates effective energy absorption by the foam.  
- **Analysis**: The foam effectively protected the PCB by dissipating impact energy, preventing sudden jolts or excessive stress on the board.  

![](/descriptions/resources/pianka.gif)

### Variant 2: Elastomer Packaging  
- **Acceleration**: Peak acceleration values exceeded **4500 m/s²**, surpassing IPC safety thresholds.  
- **Velocity**: Higher initial impact forces caused more abrupt deceleration, indicating insufficient energy absorption.  
- **Analysis**: Although the elastomer provided some cushioning, it was less effective than foam, exposing the PCB to potentially damaging forces.  

![](/descriptions/resources/guma.gif)

---

## Conclusions  
1. **Foam Packaging**:  
   - Demonstrated superior protective capabilities by effectively reducing impact accelerations and velocities.  
   - Ensured the PCB remained within safe operating limits during a drop impact.  

2. **Elastomer Packaging**:  
   - Provided limited protection, with acceleration levels exceeding safety standards, posing a risk of mechanical damage to the PCB.  

3. **Insights**:  
   - The study highlights the importance of material selection in designing protective packaging for sensitive electronics. Foam offers better energy absorption, making it ideal for mitigating drop impacts in real-world scenarios.  

---

More project details are in attached pdf file: 

[Project Deatils](https://github.com/nbssss/AbaqusProjects/blob/main/descriptions/resources/PCB_NataliaBorysowsa-Sleczka.pdf)
