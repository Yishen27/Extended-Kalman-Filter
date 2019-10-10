# Extended-Kalman-Filter
----
This is a Udacity project aiming at generating **an Extended-Kalman-Filter program in c++** that can predict the status of a moving object according to
radar and lidar data. The codes take in noisy radar and lidar data, return the predicted next status, including the position and velocity of the moving object and the corresponding RMSE (root-mean-square error) values. The program showed a basic form of perception method with **sensor fusion** on self-driving car. When connected to the simulator (https://github.com/udacity/self-driving-car-sim/releases), a live-image of priding state can be generated.


## Program performance
The program reached RMSEs for x postion, y position, x velocity, y velocity lower than 0.11, 0.11, 0.52, 0.52, respectively.
 
 ## File structure
 
 ### Folder *src*
 
 This is the folder contains all c++ files consititute the program.
 
 - FusionEKF.cpp and FusionEKF.h
   
   Code for implementing sensor fusion and corresponding header. `FusionEKF.cpp` initialize variables and matrices, initialize the Kalman filter position vector with the first sensor measurements, and call the update step for either the lidar or radar sensor measurement.
   
 - kalman_filter.cpp and kalman_filter.h
 
    `kalman_filter.h` defines the kalman_filter class. `kalman_filter.cpp` contains functions for the prediction step as well as the Kalman filter update step (lidar) and extended Kalman filter update step (radar).
 
 - tools.cpp and tools.h 
 
    `tools.cpp` implement functions to calculate root mean squared error and the Jacobian matrix. `tools.h` is the corresponding header.
    
 - main.cpp 
 
   Communicates with the Simulator receiving data measurements, calls a function to run the Kalman filter, calls a function to calculate RMSE.
   
 - measurement_package.h
 
    Defines the measurement_package class stores the measurement data.
 
 
### UD_README.md
 
 The original readme file of this project.
 
