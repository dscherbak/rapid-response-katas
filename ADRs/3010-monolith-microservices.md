# Monolith/Microservices

## Context:

The current design of the system consists of six microservices that allow for scaling, maintenance, and independent development:

- Notifications Service
- Observations Service
- Identity Service
- External Labeling Service
- ML Candidates Service
- Camera Feed Engine

Since we have a small number (hundreds) of users, a microservices architecture may not be fully justified.

## Decision:

We have decided to integrate five of our six microservices (excluding the Camera Feed Engine) into a cohesive monolithic setup while keep the ability to communicate through messaging. If one of the services needs to scale individually, it can be easily done since its component in the monolith can be easily extracted into its own microservice.

The Camera Feed Engine will remain a separate and critical component of our architecture. It will run independently and will be optimized for dynamic scaling based on factors such as the number of cameras available and message delivery rates.


<p align="center">
    <img src="../images/separate.png" alt="image" width="600" height="auto">
     <br/>
    Microservices setup
</p>


<p align="center">
    <img src="../images/monolith.png" alt="image" width="600" height="auto">
    <br/>
    Monolithic setup
</p>

The Camera Feed Engine represents a critical service within our architecture. It is designed to operate independently and is optimized for dynamic scaling based on various factors, such as the number of cameras available and the rates of messages delivered from cameras. This design ensures that this service can efficiently handle varying workloads while remaining separate from the monolithic setup.

## Rationale:

This decision is made based on requirements, which state hundreds of users. By integrating the majority of our microservices into a monolithic setup, we can reduce the complexity associated with microservices communication and maintain specialized scalability for the Camera Feed Engine.

## Status:

Approved