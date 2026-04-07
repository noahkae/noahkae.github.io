---
layout: project
title: 'Formula SAE Motor Controller Mount'
caption: Design, analysis, and manufacturability‑driven iteration
date: '20-01-2024'
image:
  path: /assets/img/projects/UCR-01.jpg
links:
  - title: UCalgary Racing Site
    url: https://ucalgaryracing.ca/
sitemap: false
accent_color: '#b40001'
accent_image:
  background: '#b40001'
theme_color: '#000000'
sitemap: false
featured: false
---
In 2023, I joined [UCalgary Racing](https://ucalgaryracing.ca/), The University of Calgary's Formula SAE team, as a member of the drivetrain subteam. One of my first major engineering responsibilities was the design of a structural mount for the [Bamocar D3](https://www.unitek-industrie-elektronik.de/wp-content/uploads/BAMOCAR-PG-D3-700-400_EN.pdf) motor controller, a high‑voltage power electronics component weighing 8.5 kg that required support under dynamic loading.

### Initial Motor Controller Mount Design

At the start of the design process, the chassis was still in development requiring the use of conservative assumptions to prioritize robustness. The mount was designed to a target 2.5 g bump load, representing worst-case dynamic conditions when driving.

![Mount view](\assets\img\projects\bamocar_mount.jpg)
The mount holding the Bamocar D3 motor controller
{:.figcaption}

Hand calculations were used to size structural members and fasteners based on first-principles to ensure adequate strength and stiffness. The geometry was then created in SolidWorks, ensuring frame compatibility while maintaining electrical and cooling accessibility. Finite element analysis was used to validate hand calculations, identify stress concentrations, and remove redundant material.

![Mount FEA](\assets\img\projects\bamocar_mount_fea.jpg)
Finite element analysis of the mount, revealing minimal displacement under load
{:.figcaption}

The final design met the target factor of safety with minimal displacement, confirming the motor controller remained secure under dynamic loads. While the design was lightweight and structurally robust, it relied on welding complex geometry, resulting in higher fabrication time and slower design iteration.

### Manufacturability-Oriented Redesign

Having exceeded strength and weight targets, I revisited the motor controller mount with an emphasized focus on manufacturability and adaptability. The redesign brought several key improvements, including:

- Simplified geometry: Complex plates and welded features were replaced with square aluminum bar stock, reducing manufacturing time.
- Serviceable fastening strategy: The motor controller was secured using rivnuts, improving serviceability and assembly speed.
- Continued structural strength: Hand calculations and FEA confirmed strength and stiffness targets were still met.

![Final Mount FEA](\assets\img\projects\bamocar_mount_fea.jpg)
Finite element analysis of the simplified mount
{:.figcaption}

![Final Mount](\assets\img\projects\bamocar_mount_fea.jpg)
The manufactured final motor controller mount
{:.figcaption}

Despite the simplifications, the redesigned mount maintained the same mass as prior designs while dramatically improving manufacturability. The final mount was manufactured and installed on the vehicle, where it performed as intended while driving and during servicing.

### Key Takeaways and Skills
- Designed structural automotive components around changing system constraints
- Balanced strength, weight, and manufacturability through iterative design
- Validated and optimized designs using hand calculations and FEA
