---
layout: project
title: "MAE 3270 Final Project: Torque Wrench Design"
subtitle: ""
tags: [materials, fem, analysis]
---

### Summary
The final project in MAE 3270 was to design a torque wrench. The wrench design needed to attain at least 1.0 mV/V output at the rated torque of 600 in-lbf, have a safety factor of Xo = 4 for yield or brittle failure, a safety factor of XK = 2 for crack growth from an assumed crack of depth 0.04 inches, and a fatigue stress safety factor of XS = 1.5. I wrote a MATLAB script to determine a design that would meet these parameters, made a CAD model in Fusion 360 and created a Finite Element Model (FEM) with Ansys Static Structural of my design.
---

### 1) CAD Model
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Wrench CAD model.png" alt="Wrench CAD model" class="project-image" style="width:100%;">
</div>

---

### 2) Material & Relevant Mechanical Properties
The material used is a high-strength, low-alloy steel: AISI 4340 Quenched and Tempered. I used Ansys Granta to obtain the mechanical properties. The elastic modulus of the material is 30.5e6 psi, the Poisson’s ratio is 0.33, the tensile strength is 240E3 psi, the fracture toughness is 82.8e3 psi (in^½), and fatigue strength from Granta for 10^6 cycles is 100E3 psi.

---

### 3) Finite Element Model Setup (Loads and Boundary Conditions)
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Loadsandboundaryconditions.png" alt="Loads and boundary conditions" class="project-image" style="width:100%;">
</div>
- Summary: The four faces highlighted in green on the block were constrained to have zero displacement and the end of the wrench handle has a 600 lbf*in load applied perpendicular to its face.

---

### 4) Normal Strain Contours
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Normal Elastic Strain.png" alt="Normal strain contours in gauge direction" class="project-image" style="width:100%;">
</div>


---

### 5) Maximum Principal Stress Contour
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Maximum Principal Stress.png" alt="Maximum principal stress contour" class="project-image" style="width:100%;">
</div>

---

### 6) FEM Results Summary

#### 6.1 Max Normal Stress (σ_max)
- **1.0371E5 psi** at stress concentrations that occur on the block above the drive

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/MAXnormalwithmark.png"
       alt="Max normal stress contour from FEM">
</div>

---

#### 6.2 Deflection at Load Point (δ)
- **1.0442 inches** at load point

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/TotalDeformation.png"
       alt="Deflection field and load-point displacement">
</div>

---
<!--
#### 6.3 Strain at Gauge
- **Value:** **1599.3 µε** at **[gauge location ref]**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/strainGauge.png"
       alt="Strain at Gauge 1 location (gauge-axis component)">
</div> -->

#### 6.3 Strain at Gauge
- **174.18 µε** at strain gauge location

<div style="display:flex; gap:1rem; clear:both; width:100%; margin:1rem 0 2rem;">
  <!-- Main image (~2/3 width) -->
  <div style="flex:2 1 0; min-width:0;">
    <img src="{{ site.baseurl }}/assets/images/materials-final/Strainatgauge.png"
         alt="Strain at gauge location (field view)"
         style="display:block; width:100%; height:auto;">
  </div>

  <!-- Secondary image (~1/3 width, a bit larger) -->
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/materials-final/strainGaugeZoom.png"
         alt="Strain gauge zoom / vertical detail"
         style="display:block; width:100%; height:auto;">
  </div>
</div>





---

### 7) Torque-Wrench Sensitivity (mV/V)
- From question 6, the measured strain from the strain gauge is **174.18 µε**
- Bridge setup used: **half**
- Gauge factor: **K = 2**
- **Sensitivity: 1.7418 mV/V** - which is larger than 1.0 mV/V so it meets the required criteria


---

### 8) Strain Gauge Selection (type & dimensions)
- Type / Part #: **Linear Strain Gauge/ C5K-06-S5145-350-33F** https://www.digikey.com/en/products/detail/micro-measurements-division-of-vishay-precision-group/C5K-06-S5145-350-33F/9857835
- Resistance: **[350 Ω]**
- Dimensions overall **L × W:** **3.1mm × 2.6mm**
- Temperature range: **-75 ~ 205°C**

<div class="image-wrapper-large">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Gauge.jpg" alt="Gauge footprint overlay" class="project-image" style="width:100%;">
</div>
