# 2-D-Steady-State-Heat-Conduction-Solver
A MATLAB-based application that numerically solves and visualizes the steady-state heat conduction equation in 2-D space with localized heat generation using the finite difference method.
# 2-D Steady-State Heat Conduction Solver

## Overview
This repository contains a MATLAB application designed to numerically solve the steady-state heat conduction equation with heat generation in 2-D space. The project was developed for the EEE 212 Numerical Technique Laboratory course at the Bangladesh University of Engineering and Technology (BUET). 

The application utilizes the finite difference method to approximate the temperature distribution across a rectangular domain. This allows users to analyze heat transfer mechanisms and visualize the effects of localized heat generation.

## Theoretical Background
Steady-state heat conduction refers to a state in which the temperature gradient within a material is constant over time, resulting in no net heat flow. The governing differential equation for 2-D steady-state heat conduction with internal heat generation is:

$$\frac{d^2T}{dx^2} + \frac{d^2T}{dy^2} + \frac{g}{K} = 0$$


To solve this equation analytically, the finite difference method discretizes the 2-D domain into a grid of nodes. Using Taylor series expansions and neglecting higher-order terms, the differential equation is converted into the following algebraic equation:

$$T(i,j) = \frac{T(i+1, j) + T(i-1, j) + T(i, j+1) + T(i, j-1)}{4} + \frac{g \cdot dx^2}{4K}$$


The program iteratively solves this algebraic equation until the error falls below a defined tolerance threshold (`Epsilon = 1e-5`).

## Application Features
The graphical user interface is built using MATLAB App Designer (`classdef heateqnsolver < matlab.apps.AppBase`) and provides the following interactive capabilities:
* **Customizable Domain:** Users can define the geometry of the rectangular plate by inputting its width (`W`) and height (`H`).
* **Boundary Conditions:** Allows custom temperature inputs for all four sides of the plate (Upper, Lower, Left, Right).
* **Heat Source Configuration:** Users can define the power of the heat source in Watts (`P`) and pinpoint its exact `(x, y)` coordinate location.
* **Thermal Conductivity:** Adjustable thermal conductivity parameter (`k`) for simulating different material properties.
* **Advanced Visualization:** Generates both 2-D contour plots and 3-D surface plots of the resulting temperature distribution using the `jet` colormap.

## Practical Applications
Understanding and solving steady-state heat conduction is critical for optimizing heat flow and system performance across various engineering fields:
* Designing thermal insulation for buildings and appliances.
* Optimizing heat exchangers in power plants and cooling systems.
* Developing electronic cooling systems to prevent overheating.
* Designing systems to extract geothermal energy efficiently.
