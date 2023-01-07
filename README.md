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
 
 ![image](https://user-images.githubusercontent.com/118617819/211164574-e9bfaaaf-0b5c-4b2d-a70a-37b2a279c745.png)

In the terminal phase, the 9M723 rocket is affected by overloads of up to 30g. However, these are temporary overloads, and for most of the maneuver the overload does not exceed 10g. The characteristics of the overloads acting on the missile depend on the maneuvers occurring.

![image](https://user-images.githubusercontent.com/118617819/211164593-7c2fc664-1859-4742-828f-e7929087de1e.png)

## Maneuverability
When analyzing the final phase of the rocket's flight, one should pay attention to the maneuverability of the 9M723 missile. Studies have been carried out to what extent the rocket can change its trajectory during the flight. The graphs below illustrate to what extent Iskander can deviate its trajectory for the same initial values in the boost phase.

![image](https://user-images.githubusercontent.com/118617819/211164637-d134d25b-0c6e-40d0-bd6f-8ca599983827.png)
![image](https://user-images.githubusercontent.com/118617819/211164642-ef4ee941-5369-495c-ae52-5d9dbd9e23c1.png)
![image](https://user-images.githubusercontent.com/118617819/211164659-f60f0235-26e0-4e6a-a17a-cf9e7c858e9c.png)

Figure below presents the Footprint, i.e. the surface on which the 9M723 Iskander rocket can aim, assuming that it was initially supposed to reach the target with coordinates [0,0] (the cross in Figure). It can be noticed that the closer the target is to the launch point of the rocket, the footprint is bigger. This means that the rocket can change its trajectory to a greater extent in the final phase of flight. The difference in surface area in the figure below for different ranges results from the rocket's stay in the lower parts of the atmosphere, as well as from the speed at which the rocket enters the terminal phase.

![image](https://user-images.githubusercontent.com/118617819/211164765-5b954d72-7179-47bd-8fcc-efb78db7d96d.png)

## Flight time
An important parameter is the duration of the rocket's flight. The rocket flight time is approximately proportional to the distance to the target, as shown in figure below. The dashed red line is an estimate because the rocket can reach the target by performing different maneuvers and taking different trajectories. The range of the estimation error is indicated by a glow around the line. The different value of the estimation error for different distances results from different maneuverability depending on the range.

![image](https://user-images.githubusercontent.com/118617819/211164807-aab2cabf-a48b-4257-ba1c-6144144028ad.png)

From the point of view of missile defense (e.g. of the Patriot system), an important parameter is the time spent by the 9M723 rocket in the terminal phase. Figure below shows the time spent by the Iskander rocket in space for altitudes below 20 km. Different time values can be noticed for different rocket trajectories, as well as for different distances to the target.

![image](https://user-images.githubusercontent.com/118617819/211164857-55093d54-8547-43c9-acb0-bd87004157fd.png)

# Conclusions
The 9M723 Iskander missile is undoubtedly a major threat to the protected facilities. The simulations show that the rocket can take different trajectories to the same target, which significantly hinders the prediction of the flight path. The range of the Iskander rocket is determined mainly by the launch phase, where gas-dynamic control is performed by means of deflectors deflecting the stream of gases coming out of the engine nozzle. The maneuvers performed do not significantly change the trajectory of the flight in the midcourse phase, but it is enough to change the projectile's range by up to 50 km. The rocket achieves its greatest maneuverability in the terminal phase, where aerodynamic control is used. In this phase, the projectile can reach an overload of up to 30g, but it should be mentioned that this is a momentary overload. The terminal velocity of the 9M723 missile is mainly dependent on the range to the target and the number of maneuvers. On the one hand, the maneuverability of the missile makes prediction difficult, but it causes the missile to lose speed, which can greatly affect the performance of missile defense. Maneuvering by the 9M723 missile also means that the missile stays in the anti-missile threat zone for longer. The rocket flight lasts up to 6 minutes over a distance of 575 km, which is due to the fact that the Iskander rocket maintains a speed of about Mach 7 in the middle phase.
