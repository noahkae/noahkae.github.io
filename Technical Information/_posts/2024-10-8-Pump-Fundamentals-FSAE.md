---
layout: post
title: Pump Fundamentals for FSAE Electric Powertrain Development
description: >
  A high-level introduction to pump fundamentals for FSAE EV.
image: 
  path: /assets/img/blog/guide.jpg
sitemap: false
---

<!--excerpt-->

This post serves to document the basics of pumps specifically for use in FSAE electric vehicles. Much of the information and the graphics used are from [this great resource by IEM.](https://iem.ca/pdf/resources/Fundamentals%20of%20Pumps.pdf) The information in this post is subject to change as development of the [UCalgary Racing](https://ucalgaryracing.ca/) UCR-02 commences, and as seen relevant. This overview is fairly basic, and should serve as a starting point for any new FSAE team members to understand pumps.

-  Table of Contents
{:toc}

# Types of Pumps

A pump is defined as a device which gives energy to a flowing liquid such that the liquid can overcome the hydraulic resistance of a connected system. In essence, pumps convert mechanical energy to hydraulic energy.
Pumps can be categorized as follows:
```
Pumps
│
├── Positive Displacement Pumps (PDPs)
│   │
│   ├── Rotary Pumps
│   │   │
│   │   ├── Single-Motor Pumps
│   │   │   ├── Vane-Based Pumps
│   │   │   └── Piston-Based Pumps
│   │   │
│   │   └── Multi-Motor Pumps
│   │       ├── Gear-Based Pumps
│   │       └── Lobe-Based Pumps
│   │
│   └── Reciprocating Pumps
│       ├── Piston Pumps
│       ├── Plunger Pumps
│       └── Diaphragm Pumps
│
└── Dynamic Head Pumps (DHPs)
    ├── Axial Pumps
    └── Centrifugal Pumps
```


## Positive Displacement vs. Dynamic Head Pumps

Positive displacement pumps displace a fixed volume, and generally produce high pressures with low flow rates. PDPs usually see use in oil systems of heavy machinery like excavators and cranes.

Dynamic head pumps increase the kinetic energy of the flow, creating low pressures while producing a high flow rate. DHPs frequently see use in liquid transport such as mains water pumping. **For the purposes of FSAE EV, this article will focus on DHPs (Centrifugal pumps specifically), as they are generally the correct option in creating efficient EV cooling systems.**

# Centrifugal Pumps

## Parts of a Centrifugal Pump

Centrifugal pumps consist of a stationary pump casing and an impeller mounted on a rotating shaft.

![Centrifugal Pump Diagram](\assets\img\blog\pump_guide_assets\centrif_diagram.jpg)

A basic centrifugal pump diagram.
{:.figcaption}

### The Casing
 
- The pump casing guides the liquid from the suction connection to the center (or eye) of the impeller.
- The pump casing provides a pressure boundary for the pump and has channels to direct the suction and discharge flow.
- The casing usually has suction and discharge holes on the main flow path of the pump.
- It also has small drain and vent fittings to remove gases trapped in it or to drain the pump for maintenance.
- Due to the impeller, fluid is pushed to the outer periphery of the casing and collected in the *volute*.
- The volute is a region that expands in cross-sectional area as it wraps around the casing, collecting discharged liquid and reducing velocity to create static pressure before pump discharge.

### The Impeller

- The impeller imparts radial motion on the fluid, pushing it to the outer part of the casing.
- Impellers are classified based on the number of points that the liquid can enter into and the amount of webbing between the blades.
- Impellers can either be single or double-suction:
    - Single-suction impellers only allow liquid to enter from one side.
    - Double-suction impellers allow the liquid to enter from both sides at once.
- Impellers can be open, semi-open, or enclosed. This is easiest to explain visually:

![Types of impellers](\assets\img\blog\pump_guide_assets\impeller_types.jpg)

A visual explanation of the three main categories of impellers.
{:.figcaption}

### Diffusers

- A diffuser is a set of stationary vanes that surround the impeller.
- Diffusers increase efficiency by allowing more gradual expansion of the flow path whilst reducing turbulence during velocity reduction.
- Diffuser vanes are designed such that liquid exiting them encounters ever-increasing flow area and thus a decrease in flow velocity, converting kinetic energy to flow pressure.

![Vanes](\assets\img\blog\pump_guide_assets\diffuser.jpg)

A basic illustration showing a pump diffuser.
{:.figcaption}

## Types of Centrifugal Pumps

The driving theory behind centrifugal pumps is the generation of centrifugal force in the liquid medium. Blades are curved in three main ways being: backward curving, radial, and forward curving.

![Blade Curves](\assets\img\blog\pump_guide_assets\blade_curves.jpg)

An image showing the three types of blade curvature.
{:.figcaption}

- The use of radial and forward curving blades means that the pump's power requirement necessarily increases with discharge.
    - The pumps are prone to underutilization and thus are often used inefficiently.
    - Exceeding the design flow rate may cause overloading and motor failure.

- Backward curving blades have unique *"self-limiting"* power characteristics that protect the motor from overload.
    - Backwards curving blades actually see a reduction in power consumption with excess flow rate.
    - Pumps using this design can handle a range of flow rates without problems.
    - The design point of a backwards curving design is located at the flow rate where maximum efficiency occurs.

![Pump blade efficiency curves](\assets\img\blog\pump_guide_assets\pump_curves.jpg)

Diagrams showing the differences between blade curvatures. H is pump resistance, P is power input, and Q is liquid flow rate.
{:.figcaption}

## Centrifugal Pump Performance

Pump performance is found by obtaining test data and many different flow rates. Pump efficiency is given as follows:

$$
\begin{aligned}
  P_{sh} = \frac{PQ}{\eta} = \frac{\rho ghQ}{\eta}
\end{aligned}
$$

Where P<sub>sh</sub> is shaft power input, P is the pressure difference across the pump, and h is the manometric head difference across the pump.

![Flow rate vs variables](\assets\img\blog\pump_guide_assets\q_graphs.jpg)

Diagrams showing the impact of flow rate on various variables.
{:.figcaption}

### Operating Point

The operating point is the point at which the force of the pump balances the total resistance of the system. This point occurs at the intersection between the performance and system resistance curves. **You will need to consult this extensively when developing an FSAE EV cooling system.**

![Operating point graph](\assets\img\blog\pump_guide_assets\o_point.jpg)

Diagram showcasing an operating point.
{:.figcaption}

### Controlling Flow Rate

To lower flow rate, system resistance can be increased by partially closing the pump delivery valve. This is the easiest and cheapest method, but significantly increases system losses.

The most power efficient way to control pump flow is through shaft speed control. While this method of controlling flow rate is more expensive, it grants increased efficiency when compared to pump delivery valve manipulation. Operating pumps at higher shaft speeds shifts the power curve upwards, which can lead to the motor overheating.

![Valve vs motor speed](\assets\img\blog\pump_guide_assets\losses.jpg)

The effects of pump delivery valve manipulation (left) vs. motor shaft speed manipulation (right).
{:.figcaption}

### The Best Efficiency Point

The best efficiency point (BEP) also known as the normal flow point, is the point at which the pump operates at the maximum possible efficiency, and is the normally targeted point for pump operation.

![BEP](\assets\img\blog\pump_guide_assets\bep.jpg)

A visual representation of the BEP.
{:.figcaption}

### Operating Range

Operating a pump beyond its BEP decreases efficiency and leads to mechanical and hydraulic issues. Thus, it is recommended to operate pumps within 15% of their BEP.

- Pumps should never be operated at a flow rate less than 60% of their BEP as vibrations at this state can cause bearing damage.

- Pumps should also never exceed 120% of their BEP as the risk of cavitation and total impeller destruction increases greatly at this point.

![Operating Range](\assets\img\blog\pump_guide_assets\range.jpg)

What the safe operating range of a pump looks like on a system resistance vs flow rate curve.
{:.figcaption}

## Motor Selection

Pump motors are selected based on the maximum shaft power, which is determined using the shaft power curve of the pump. A 15% safety margin is typically used when selecting the motor.

![Motor power curve](\assets\img\blog\pump_guide_assets\shaft_pc.jpg)

A shaft power curve for a pump.
{:.figcaption}

## Cavitation

The phase of a substance is a function of both temperature and pressure, and the pressure at which a liquid evaporates at a given temperature is called the **vapor pressure**. If the pressure drop between the pump suction and the impeller eye is too large or the temperature of the pump is too high, the liquid may flash to vapor.

The vapor bubbles created in such conditions are swept along the vanes by the liquid flow, and upon reaching an area of greater pressure than the substance's saturation pressure, they collapse. This process is called cavitation.

![Cavitation diagram](\assets\img\blog\pump_guide_assets\cav_mech.jpg)

An illustration showing the cavitation mechanism.
{:.figcaption}

Cavitation degrades pump performance, creating fluctuations in flow rate and discharge pressure. The vapor bubbles typically collapse after contacting the leading impeller vane, creating microscopic pits on it. The accumulation of these pits can destroy an impeller if allowed to continue for considerable periods of time. Pumps undergoing cavitation tend to sound like a can of marbles being shaken.

![Cavitation result](\assets\img\blog\pump_guide_assets\cavitation.jpg)

The effect of cavitation on a metal surface. Credit: [Wikipedia](https://en.wikipedia.org/wiki/Cavitation#/media/File:Cavitation_Propeller_Damage.JPG).
{:.figcaption}

### Net Positive Suction Head

To avoid cavitation, pressure at all points within the pump must remain above the saturation pressure. The net positive suction head (NPSH) is used to determine if the aforementioned requirement is being met.

- The net positive suction head available (NPSHA) is equivalent to the difference between the suction and saturation pressures.

- The net positive suction head required (NPSHR) is the minimum NPSH required to avoid cavitation.

- To avoid cavitation, NPSHA should be greater than NPSHR.

A mathematical representation of NPSH follows:

$$
\begin{aligned}
  h_{atm} - h_{vap} - H_{ss} - h_{ls} - \frac{V_s^2}{2g} > NPSH 
\end{aligned}
$$

Where the left side of the inequality represents NPSHA and the right side represents NPSHR. 

### Prevention

Cavitation is prevented by:

- Raising the suction tank liquid level.

- Decreasing losses of friction and eddy types by:
    - Decreasing suction pipe length.
    - Increasing suction pipe diameter.
    - Excluding unnecessary fittings.
    - Using suction valves that minimize losses.

## Pump Priming

If a dynamic head pump is placed above the suction tank fluid level, it cannot start until its impeller is flooded by liquid. The centrifugal force generated by the impeller directly depends on the density of the fluid within it, and the density of air is too low to create the suction pressure necessary to draw the heavy liquid from the tank into the pump.

Some pumps are self priming, but if you're working on an FSAE EV cooling system, you'll just have to suck the fluid through the system before running it.

## Typical Installation Layout

![typical installation](\assets\img\blog\pump_guide_assets\diagram.jpg)

An illustration showing a very typical centrifugal pump installation configuration.
{:.figcaption}