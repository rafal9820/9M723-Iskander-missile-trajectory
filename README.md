# 9M723-Iskander-missile-trajectory
![image](https://user-images.githubusercontent.com/118617819/210845000-a1477696-95df-4cc5-beb9-3b962e8b5ccd.png)

## Introduction 
The project presents the results of flight simulation tests of the 9M723 Iskander aeroballistic missile. Simulation studies were carried out using Matlab&Simulink software tools based on the developed physical and mathematical model of the rocket's motion in the Earth's atmosphere. In order to conduct reliable tests, the aerodynamic and inertial coefficients were determined on the basis of the parameters and estimated dimensions of the 9M723 rocket. The model of the atmosphere was implemented in accordance with the International Standard Atmosphere ISO 2533. The test results were visualized using Python programming language libraries for various scenarios of controlling the flight trajectory of the 9M723 aeroballistic rocket. Matlab ver. 2022a was used.
## Research methodology
The research was carried out based on the developed physical and mathematical model of the rocket flight in the Earth's atmosphere.
First of all, the dimensions of the individual elements of the rocket were estimated on the basis of available technical drawings and the elements of the control and guidance apparatus of the 9M723 rocket were analyzed. In order to determine the mass of the rocket after the fuel of the rocket motor has burnt out, the Tsiolkovsky equations were used, which determine the speed of the rocket that consumes fuel during the flight, i.e. the rocket that changes mass. Estimation of the dimensions of the airframe and knowledge of the mass of the projectile before and after fuel burnout made it possible to determine the aerodynamic and inertial characteristics of the rocket for all phases of flight using the Prodas and Autocad software. The model of the atmosphere was implemented in accordance with the International Standard Atmosphere ISO 2533, which defines the parameters of the atmosphere for an altitude of -2 km to 80 km above sea level. Parameters of the atmosphere for an altitude above 80 km have been interpolated. The mathematical model of the rocket's motion is based on 12 differential equations describing the translational and rotational motion of the object with set parameters.
The rocket flight control model was developed on the basis of available data and assumptions. It was assumed that the launch phase lasts 50 s, where the rocket engine produces the estimated thrust. It was assumed that in the launch phase the rocket is gas-dynamically controlled (thrust vector), as the gas-dynamic rudders are located directly behind the engine nozzle. Aerodynamic control was used only in the middle and terminal stages. The control of the 9M723 rocket is based on programmable control over the entire length of the flight and self-guidance using the proportional navigation method in the terminal phase.
Programmable control consists in implementing a fixed flight trajectory and digital maps of the terrain surface into the on-board equipment. During the flight, the rocket, using gyroscopes, accelerometers and the GPS module, compares the current position of the object in relation to the programmed flight trajectory and develops control signals based on deviations from this trajectory. During the terminal phase, the optoelectronic or radar head on board the rocket compares digital maps of the terrain surface with the real image of the terrain, correcting its trajectory.
## Repository description
#### aerodynamic_characteristics folder
Contains Matlab files (.m; .mlx) and Prodas_files folder. Data from Prodas software are included in the Prodas_files folder. Matlab files represents determined aerodynamic characteristics using data from Prodas software.
#### atmosphere_model folder
Contains Matlab files (.m; .mlx). Matlab files represents determined atmosphere model.
#### mass-inertia_parameters folder
Contains Matlab files (.m; .mlx) and .mpr folder. Data from AutoCad software are included in the folder. Matlab files represents determined mass-inertia characteristics using data from AutoCad software.
#### matlab_model folder 
Contains Matlab files (.m; .mlx), Simulink files (.slx) and simulink_screenshoots folder. Simulink file (simulation_model.slx) contains the entire mathematical model of the missile's motion. Matlab file shows an exemplary simulation with given initial conditions.
#### python_analysis folder
Contains Jupyter Notebook file (.ipynb) and data_from_matlab folder. Jupyter Notebook file contains an analysis of the parameters of the Iskander rocket trajectory based on data from simulations for various variants of manoeuvres.
