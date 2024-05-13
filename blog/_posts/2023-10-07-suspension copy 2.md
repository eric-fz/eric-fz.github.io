---
layout: post
title: "2023-2024: Suspension Design for Formula Style Racecar"
truncated_preview: true
excerpt_separator: <!--more-->
---
### Overview

![SuspensionGif](/SuspensionGif.gif)
![SuspensionRL](/SuspensionRL.png)
![SuspensionCAD](/suspensionfullcad.png)

Since June, I have been working with the MIT Motorsports Formula SAE Team to design the entirety of the suspension system for the Model Year 2024 car. The design process for each subsystem begins with vehicle dynamics and kinematics, geometric constraints, and team goals, and with these factors, we set specific design requirements. We then follow a series of design reviews as the subsystems develop from various conceptual architectures to fully-fledged CAD models, to physical parts in January. The suspension team simulates tire properties and suspension geometry using Matlab, OptimumK, and Optimum Tire. For CAD, CAM, and FEA we use Siemens NX. All parts on the suspension system are machined in-house using our HAAS CNC Mill, manual lathes, and 3D printers. To validate the simulated vehicle dynamics and load cases, various sensors were implemented onto the physical car. These included an IMU, strain gauges on the control rods, and shock potentiometers. Attached is the [design binder](/MY24%20Suspension%20Design%20Binder.pdf) for the suspension, as well as a [poster](/SuspensionDeFlorez.pdf) I submitted to MIT's DeFlorez Mechanical Engineering Awards. 

<!--more-->

As suspension lead, managed a team of over 10 members to design, manufacture, and test the pull rods, ARBs, rockers, and steering, starting from first principles. I was also of determining our suspension point geometry and choosing our tires, both vital for optimizing both lateral and longitudinal acceleration for the racecar, as well as maintaining driver comfort. 

![TireFits](/tires.png)
*Tire models fit using Tire Testing Consortium data and Pacejka's Magic Formula 6.2.*

This highly iterative process requires constant communication with the chassis, powertrain, and aerodynamics teams in order to eliminate packaging conflicts and optimize the suspension system with ever-changing car parameters. Designing the suspension geometry began in early August, and the design freeze is in the last week of October. After October, I will be working mainly on validating my design through finite element analysis, as well as testing our control arms physically using an Instron tensile tester. Documentation of the entire design process is expected, to ensure proper knowledge transfer, to both current and future new members. Some specific innovations we are implementing this year included modeling suspension compliance/deflection, and writing a caster optimization script.

![SuspPoints](/suspoints.png)
*MY24 Suspension Points v4*

One challenge I’ve faced in the design process so far is determining our car’s camber sensitivity: how much a deviation from optimal camber affects cornering performance, and how that translates to competition points. The entire wheel packages team was blocked, as this sensitivity was required to determine stiffness requirements of the wheel packages, as any deflection from external loads impacts camber. Even though the design requirements deadlines rapidly approached, I made sure that every design decision was traced back to vehicle dynamics, either through Excel sheet calculations, or lap time simulations. In the case of determining camber sensitivity, I worked with the Simulations Lead to run a camber deflection vs. lap time sensitivity simulation in steady-state cornering. It was determined that 1 degree of camber change due to deflection equated to 3/575 points lost. This simulation has helped us contextualize our design requirements and set a wheel packages stiffness requirement to 1 degree in combined bump + cornering loads.

![cambscript](/camberscript.png)
*Camber script in Lapsim*

I've also had the opportunity to apply the formulas I've learned in my Mechanics and Materials I and Physics classes to size many of the suspension components. Most notably, I helped rework our suspension rod sizing calculations from first principles, as our push rods have buckled in previous years due to inaccurate sizing. First, I helped determine the maximum load cases each suspension rod faces, starting from measured values of maximum bump loading (3kN), acceleration (1.5G), braking (2G), and lateral load transfer. We utilized FSAEillumina's [excel spreadsheet](https://fswiki.us/Suspension_Forces), which uses matrix math to represent each control rod as a vector, and each load case as a matrix of three-dimensional loads. This spreadsheet takes in the coordinates of each control rod end point and tire forces, and outputs the maximum tension and compression each rod will experience. From this spreadsheet, I worked with the A-arms subsystem lead to calculate the yield strengths for different rod radii/material under bending, euler buckling, tension, and compression. The largest source of stress is from the pull rod, which isn't connected directly to the wheel packages, but to a connection on the A-arm itself. The vertical force caused by the pull rod creates a non-negligble bending moment on the upper A-arms, which we sized conservatively for, and are also planning on performing FEA for. Of course, these calculations cannot accurately account for possible manufacturing error, which could cause eccentric buckling, so each rod is sized with a 1.5 factor of safety, and we've developed a thorough manufacturing plan to ensure our machined components meet our tolerance requirements. 

You can find our hand calculations excel spreadsheet [here.](/Aarms.xlsm)

![MotionAnalysis](/MotionAnalysis.png)
*I performed motion analysis on our final suspension points to check for interferences with the wheel center rims*