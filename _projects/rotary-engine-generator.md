---
layout: project
title: 'Rotary Engine Generator'
caption: Geometry optimization of a rotary engine
date: '30-05-2024'
image:
  path: /assets/img/projects/felix_render.jpg
sitemap: false
accent_color: '#ffffff'
accent_image:
  background: url('/assets/img/projects/parts.jpg') center/cover
  overlay: false
theme_color: '#000000'
sitemap: false
---
When compared to conventional piston engines, the rotary internal combustion engine excels in parts count, mechanical simplicity, and power density, making it a compelling choice for compact generator applications. In cases where weight, portability, and serviceability are constraints, such as portable emergency power or automotive range extenders, the rotary architecture offers specific benefits over other designs. With this in mind, I led a team of four to design and model FELIX (Fuel Efficient Lightweight ICE), a rotary-engine generator targeting an 8000W output.

### Geometry Optimization

The first step in creating an optimized rotary engine was to develop a [Matlab script](https://github.com/noahkae/matlab_rotary_engine/blob/main/RotorShape.m) to identify the rotor and housing geometry that maximizes power output at a fixed displacement, iterating through profiles to find the optimal epitrochoidal shape for our application and returning the optimized equations. Power output was approximated based on chamber volume variation and operating frequency.

![Matlab Equations](\assets\img\projects\Rotor_eqns.jpg)
The outputs of the [Matlab script](https://github.com/noahkae/matlab_rotary_engine/blob/main/RotorShape.m) - The rotor on the left and housing on the right
{:.figcaption}


### Mechanical Design

The optimized rotor and housing profiles were brought into SolidWorks as equation-driven curves, precisely preserving the MATLAB geometry. Wall thicknesses for the rotor and housing were determined through SolidWorks Simulation to balance structural reliability against mass. Removable access panels were incorporated into the housing design to enable field servicing, a deliberate choice given the target use case of remote and portable deployment.

![Engine section view](\assets\img\projects\felix_engine_sect.jpg)

A section view of the engine within the generator
{:.figcaption}

![Felix with no panels](\assets\img\projects\felix_panels_rm.jpg)

The generator with maintenance panels removed
{:.figcaption}

The final concept generator design met the 8000W goal while achieving a weight of only 40 kg. Given more time, the most valuable next step would have been dedicated analysis of chamber sealing.
Chamber sealing is the primary limiter of efficiency and durability in rotary engines, and thermal and contact simulation of the seal geometry would have allowed us to validate the efficiency gains predicted by the MATLAB optimization and inform material selection.
