---
layout: project
title: "MAE 3270 Final Project: Torque Wrench Design"
subtitle: ""
image: assets/images/materials-final/cadRender.jpg
tags: [materials, fem, analysis]
---

### Summary
The final project in MAE 3270 was to design a torque wrench. The wrench design needed to attain at least 1.0 mV/V output at the rated torque of 600 in-lbf, have a safety factor of Xo = 4 for yield or brittle failure, a safety factor of XK = 2 for crack growth from an assumed crack of depth 0.04 inches, and a fatigue stress safety factor of XS = 1.5. I wrote a MATLAB script to determine a design that would meet these parameters, made a CAD model in Fusion 360 and created a Finite Element Model (FEM) with Ansys Static Structural of my design.
---

### 1) CAD Model
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Wrench CAD model" alt="Wrench CAD model" class="project-image" style="width:100%;">
</div>

---

### 2) Material & Relevant Mechanical Properties
The material used is a high-strength, low-alloy steel: AISI 4340 Quenched and Tempered. I used Ansys Granta to obtain the mechanical properties. The elastic modulus of the material is 30.5e6 psi, the Poisson’s ratio is 0.33, the tensile strength is 240E3 psi, the fracture toughness is 82.8e3 psi (in^½), and fatigue strength from Granta for 10^6 cycles is 100E3 psi.

---

### 3) Finite Element Model Setup (Loads and Boundary Conditions)
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Loadsandboundaryconditions.heic" alt="Loads and boundary conditions" class="project-image" style="width:100%;">
</div>
- Summary: The four faces highlighted in green on the block were constrained to have zero displacement and the end of the wrench handle has a 600 lbf*in load applied perpendicular to its face.

---

### 4) Normal Strain Contours
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/Normal Elastic Strain.png" alt="Normal strain contours in gauge direction" class="project-image" style="width:100%;">
</div>
Call out the gauge pads and the local ε values where the gauges will be bonded.

---

### 5) Maximum Principal Stress Contour
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/stress-maxP.png" alt="Maximum principal stress contour" class="project-image" style="width:100%;">
</div>
Note hotspot location, value, and margin vs. σᵧ.

---

### 6) FEM Results Summary

#### 6.1 Max Normal Stress (σ_max)
- **Value:** **[fill] MPa** at **[location]**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/stress-max.png"
       alt="Max normal stress contour from FEM">
</div>
*Notes:* [hotspot, K_t reasoning, mesh independence, margin vs. σ_y].

---

#### 6.2 Deflection at Load Point (δ)
- **Value:** **[fill] mm** at **[node/feature]**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/deflection-loadpoint.png"
       alt="Deflection field and load-point displacement">
</div>
*Notes:* [stiffness check vs. analytical beam calc, linearity].

---
<!--
#### 6.3 Strain at Gauge
- **Value:** **1599.3 µε** at **[gauge location ref]**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/strainGauge.png"
       alt="Strain at Gauge 1 location (gauge-axis component)">
</div> -->

#### 6.3 Strain at Gauge
- **Value:** **1599.3 µε** at the set gauge location

<div style="display:flex; gap:1rem; clear:both; width:100%; margin:1rem 0 2rem;">
  <!-- Main image (~2/3 width) -->
  <div style="flex:2 1 0; min-width:0;">
    <img src="{{ site.baseurl }}/assets/images/materials-final/strainGauge.png"
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
- Measured strain from the strain gauge in the model **ε = 1599.3 µε**
- Gauge factor: **K = 2**
- Bridge setup used:  **half**
- **Sensitivity: 1.5993 mV/V** - meets the required criteria


---

### 8) Strain Gauge Selection (type & dimensions)
- Model / Part #: **[fill]** (link)
- Resistance: **[120 Ω / 350 Ω]** — Gauge factor: **[fill]**
- Grid **L × W:** **[fill] mm × [fill] mm**
- Carrier/backing: **[fill]**; Temperature range: **[fill]**
- **Bonding area available on part:** **[fill] mm × [fill] mm** (fits with margin)

<div class="image-wrapper-large">
  <img src="{{ site.baseurl }}/assets/images/materials-final/gauge-footprint.png" alt="Gauge footprint overlay" class="project-image" style="width:100%;">
</div>
