# Simulation of Hot Rolling Process in Abaqus  

## Project Description  
This project focuses on simulating the **hot rolling process** of a steel billet using Abaqus. The simulation incorporates thermomechanical material properties and uses the **Johnson-Cook equation** to model plastic deformation, considering the effects of strain rate and temperature.  

The process is divided into two main steps:  
1. **Positioning**: The billet is pushed into the rolling groove.  
2. **Rolling**: The rollers deform the billet at high temperature while rotating at controlled speeds.

This simulation highlights the behavior of the billet during deformation, including stress, strain, and temperature distribution, with results that provide insights into process efficiency and potential optimization.  

---

## Execution Details  

### 1. Geometry and Assembly  
- **Billet**: A rectangular prism (160 mm x 1000 mm).  
- **Rollers**: Rigid analytical parts with a detailed groove profile.  
- **Pusher**: A component to move the billet into the rolling zone.  
- **Assembly**: The billet is aligned centrally between the rollers and placed 200 mm away from the rolling groove.  

### 2. Material Properties  
- **Elastic-Plastic Behavior**:  
  - Young’s Modulus: 210,000 MPa  
  - Poisson’s Ratio: 0.3  
- **Thermal Properties**:  
  - Conductivity, specific heat, and expansion coefficients were defined from material datasets.  
- **Plastic Deformation Model**:  
  - The Johnson-Cook equation was used to account for strain, strain rate, and temperature effects.  

### 3. Boundary Conditions and Loads  
- **Initial Temperatures**:  
  - Billet: 1100°C  
  - Rollers and pusher: 19°C  
- **Step 1**:  
  - The pusher moves the billet into position using a displacement boundary condition.  
- **Step 2**:  
  - Rollers rotate at 0.15 rad/s initially, increasing to 1 rad/s for proper deformation.  
  - Frictional contact (coefficient: 0.3) is applied between the billet and rollers.  

### 4. Meshing and Solver  
- The billet is discretized with a structured finite element mesh, respecting the **1000-node limit** of the Abaqus Student Edition.  
- **Solver**: Explicit dynamic analysis captures the transient deformation process.  

### 5. Results Visualization  

**Step 1**:

![](/descriptions/resources/s1.gif)

![](/descriptions/resources/s1_2.gif)

**Step 1 and 2**:

![](/descriptions/resources/s1_s2.gif)

![](/descriptions/resources/s1_s2_2.gif)

---

## Observations and Analysis  

### Stress and Strain Distribution  
- The highest stress concentrations were observed in the contact area between the billet and the rollers, which aligns with theoretical predictions.  
- A gradient in strain distribution was noted, decreasing toward the billet's symmetry axis, indicating non-uniform material deformation.  

### Temperature Changes  
- The temperature increased significantly in the deformation zone due to the heat generated from plastic deformation.  
- Minimal temperature differences were observed between the billet's surface and its interior, thanks to the material's high thermal conductivity.  

### Effect of Rolling Speed  
- Higher roller speed (1 rad/s in the second time step) reduced the contact time but intensified the deformation, resulting in a more uniform strain distribution.

---