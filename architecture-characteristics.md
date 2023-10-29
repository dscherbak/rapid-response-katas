# Architecture Characteristics

Considering the requirements, the following architecture characteristics are identified:

## Availability
The core functionality of the system is notifying observations in near real-time to biologists, which means that the system should be highly available. The maximum acceptable downtime is X hours per year.

## Responsiveness
The system should be responsive to Cameras' observations. The system should be able to process observations in near real-time. The maximum acceptable delay is X seconds.

## Elasticity
Based on the fact that the cameras track the movements of animals and insects, the number of observations changes based on the time of the day and/or season and tons of other natural causes. In addition, the number of cameras is increasing over time. Considering it, the system should be able to scale up and down automatically.

## Performance
The firmware of the camera should be able to process/analyze the video stream in real time. The camera is built with a combination of ultra-low-power microcontrollers, which means that the processing should be well-optimized in terms of its efficiency, speed, and resource utilization.

## Reliability
To be able to notify observations in near real-time, the system should be reliable. Meaning that the system should be able to recover from failures and continue to operate without interruption. 

## Security
The communication between a camera and the system should be secure. The system should be able to authenticate the camera, and the camera should be able to authenticate the system (model and firmware should be signed). The access to the cameras should be restricted to the specific users, as well as the access to observations.
