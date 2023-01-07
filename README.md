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
# Research results
## Boost phase
The starting phase is used to give the missile the appropriate speed and angle of inclination so that the missile can reach the appropriate range.

![image](https://user-images.githubusercontent.com/118617819/211163858-22f2be8e-9653-4859-9e2c-41fc7bb2e82f.png)

During the boost phase, the object is subjected to a thrust force, and the thrust vector can be deflected by gas-dynamic rudders. The operation of the rocket engine during the launch phase increases the speed of the object. Figure above shows a graph of the velocity in the frame associated with the object. The value of the speed after the start phase is about 2200 m/s. You can notice a decrease in the longitudinal velocity (“U”) during maneuvers (“W” - velocity perpendicular to the projectile axis).
During the starting phase, there are overloads exceeding 20g at times. This is because the missile must tilt to a predetermined angle to enter the optimal ballistic trajectory.

![image](https://user-images.githubusercontent.com/118617819/211164033-e5febcd5-f04f-46c1-8620-e8f14ecced90.png)

The launch phase mainly determines the range of the rocket, therefore the flight trajectory of the 9M723 rocket in the launch phase depends on the distance of the target. It can be noticed that the smaller the target range of the rocket, the more the rocket's trajectory "leans" relative to the plane of the Earth.

![image](https://user-images.githubusercontent.com/118617819/211164071-762d8e17-00fb-40b7-8068-1762c1170108.png)

Performing a maneuver during the boost phase leads to a loss of speed, so there is a relationship between the speed after the launch phase of the rocket and the distance to the target (range). As shown in figure above the speed after the boost phase is directly proportional to the distance to the target. The speed of the rocket after the boost phase, as well as the pitch angle of the rocket, determines the range and the value of the speed with which the rocket enters the terminal phase.

![image](https://user-images.githubusercontent.com/118617819/211164157-8dc56b09-d579-4d9a-b591-80c2d589e3ff.png)

## Midcourse phase
The midcourse phase is a transition period where the rocket moves mainly in a ballistic trajectory. The high flight altitudes mean that maneuvering with the relatively small rudders of the Iskander rocket is practically minimal. Any significant correction or change of flight trajectory may take place for altitudes below about 40 km. The correction (maneuver) in the midcourse phase is shown in figures below, where the paths of the rocket are shown for the ballistic trajectory and the trajectory with maneuvers during the midcourse and terminal phases.

![image](https://user-images.githubusercontent.com/118617819/211164289-79249cdd-e835-402b-9c38-0be8cd25b4b2.png)
![image](https://user-images.githubusercontent.com/118617819/211164297-ff42b10a-138b-472d-bd32-684183145e9f.png)

Analyzing the graphs above, it can be seen that maneuvering during the middle phase has the greatest impact on the trajectory for short distances to the target. This is due to the fact that the maximum height of the trajectory is relatively small. Also noteworthy is the flight trajectory of the Iskander rocket to targets at a distance of more than about 425 km. In such a situation, the maximum height of the trajectory exceeds 60 km, and for the maximum range (about 575 km) it reaches even 140 km. For longer distances to the target, the 9M723 rocket has less maneuverability than for targets close to the launch point of the rocket.

The speed of the rocket in the midcourse phase is determined by the range to the target and the chosen type of trajectory. In figure below three possible trajectories (“straightening” flight in the midcourse phase and “diving” in the terminal phase, ballistic, “diving” in the terminal phase) are presented for three different target ranges. Depending on the maneuvers performed, the speed of the rocket in the midcourse phase decreases. Reduced maneuverability in the midcourse phase for more distant targets can also be deduced from the graph below.

![image](https://user-images.githubusercontent.com/118617819/211164396-d8a7de0d-df55-4b71-a18f-86a2b85250d5.png)

## Terminal phase
The terminal phase is the period when the missile returns to the denser parts of the atmosphere, which allows it to maneuver using aerodynamic forces from the rudders. In this part of the flight, the missile significantly loses speed.

![image](https://user-images.githubusercontent.com/118617819/211164462-39355f42-b16f-4bd7-9b87-9307aa289378.png)

Figure above shows the graph of the terminal phase velocity for different types of rocket trajectories, which flies to the target at a distance of about 380 km. The graph shows the differences in the final value of the rocket's velocity (after reaching the target) depending on the maneuvers performed. The rocket achieves the highest speed for the ballistic trajectory. This is because the maneuvering missile loses speed. In Figure below a box plot of rocket velocity for different types of trajectories is shown. It shows that the maneuvers of the rocket to a large extent do not affect the average value of the speed of the rocket during the flight, but they have a significant impact on the final value of the speed after reaching the target.

![image](https://user-images.githubusercontent.com/118617819/211164527-da3c2b3a-0b27-4f7f-9c86-1a145153174f.png)

 The terminal velocity of the 9M723 rocket also depends on the distance to the target, which is shown in figure below.
 
 
