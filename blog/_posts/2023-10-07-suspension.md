---
layout: post
title: "Fall 2023: Suspension Design"
truncated_preview: true
excerpt_separator: <!--more-->
---
### Overview

Since June, I have been working with the MIT Motorsports Formula SAE Team to design the entirety of the suspension system for the Model Year 2024 car. The design process for each subsystem begins with vehicle dynamics and kinematics, geometric constraints, and team goals, and with these factors, we set specific design requirements. We then follow a series of design reviews as the subsystems develop from various conceptual architectures to fully-fledged CAD models, to physical parts in January. The suspension team simulates tire properties and suspension geometry using Matlab, OptimumK, and Optimum Tire. For CAD, CAM, and FEA we use Siemens NX. All parts on the suspension system are machined in-house using our HAAS CNC Mill, manual lathes, and 3D printers.

![MY18Susp](/my18susp.jpeg)
*Suspension from MIT's 2018 racecar*

<!--more-->

As suspension lead, I am managing a team of over 15 members to design the pull rods, ARBs, rockers, and steering, starting from first principles. I am also in charge of determining our suspension point geometry and choosing our tires, both vital for optimizing both lateral and longitudinal acceleration for the racecar, as well as maintaining driver comfort. 

![TireFits](/tires.png)
*Tire models fit using Tire Testing Consortium data and Pacejka's Magic Formula 6.2.*

This highly iterative process requires constant communication with the chassis, powertrain, and aerodynamics teams in order to eliminate packaging conflicts and optimize the suspension system with ever-changing car parameters. Designing the suspension geometry began in early August, and the design freeze is in the last week of October. After October, I will be working mainly on validating my design through finite element analysis, as well as testing our control arms physically using an Instron tensile tester. Documentation of the entire design process is expected, to ensure proper knowledge transfer, to both current and future new members. Some specific innovations we are implementing this year include carbon fiber control arms, modeling suspension compliance/deflection, and writing a caster optimization script.

![SuspPoints](/suspoints.png)
*MY24 Suspension Points v4*

One challenge I’ve faced in the design process so far is determining our car’s camber sensitivity: how much a deviation from optimal camber affects cornering performance, and how that translates to competition points. The entire wheel packages team was blocked, as this sensitivity was required to determine stiffness requirements of the wheel packages, as any deflection from external loads impacts camber. Even though the design requirements deadlines rapidly approached, I made sure that every design decision was traced back to vehicle dynamics, either through Excel sheet calculations, or lap time simulations. In the case of determining camber sensitivity, I worked with the Simulations Lead to run a camber deflection vs. lap time sensitivity simulation in steady-state cornering. It was determined that 1 degree of camber change due to deflection equated to 3/575 points lost. This simulation has helped us contextualize our design requirements and set a wheel packages stiffness requirement to 1 degree in combined bump + cornering loads.

![cambscript](/camberscript.png)
*Camber script in Lapsim*