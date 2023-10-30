# Architecture

In our pursuit of creating a highly adaptable and flexible software architecture, we've designed a system consisting of six core microservices. Each of these microservices is independently deployable and capable of functioning in isolation. This architecture allows us to seamlessly adapt to changing requirements while maintaining a robust and interconnected system.

![alt text](images/architecture.png)


## Identity Service

The Identity Service pis responsible for managing user identity and authentication. Its primary purpose is to establish a secure and centralized authentication mechanism.  Additionally, the service manages user access to cameras.

**External Dependencies**: None

**Message Handling**:

* Camera Registration Messages: The service processes camera registration messages, which provide camera information. Administrators use this information to grant user access to specific cameras.

**Message Generation**:

* New User Registration Message: The Identity Service generates a message when a new user is registered

## Observations Service

The Observations Service is responsible of storing observations, facilitating the labeling of unrecognized species, forwarding selected observations for AI model training, and generating CamTrap DP files.

**External Dependencies**: None

Message Handling:

* New Observation Captured: This message is processed to store the observation, making it available for users to act upon.
* Unrecognized Species Labeled: The service handles this message to maintain a labelling history for all observations and make labeled observations available to be used in AI model training.

**Message Generation**:

* New Observation Captured or Changed (Labeled): The service generates a message when a new observation is captured or when changes are made, such as labeling, ensuring that relevant updates are communicated.
* Command to Label Unrecognized Species: An outbound message (command) is produced when there's a need to label an unrecognized species using an external service.
* Command to Utilize New Training Samples: The service generates a message (command) when new training samples are ready for use in constructing a new AI model.

## Notifications Service

The Notifications Service is dedicated to delivering real-time push notifications to mobile clients, with a primary focus on providing timely updates on observations that users are subscribed to.

**External Dependencies**: Notification message delivery service

**Message Handling**:

* New Cameras Messages: The service handles these messages to manage subscriptions for new cameras, ensuring that users can receive notifications related to these cameras.
* New Users: The service manages subscriptions for new users through these messages, ensuring that notifications reach the intended recipients.
* Observations Captured: To keep users informed, this message is processed to send notifications to all subscribers when new observations are captured.

**Message Generation**: None

## External Labeling Service

The External Labeling Service communicates with external labeling services, such as Wildlife Insights.

**External Dependencies**: Wildlife Insights

**Message Handling**:
- Unrecognized Species to be Labeled Messages: The service handles these messages, attempting to label species that require identification.

**Message Generation**:
- Labeled species: Labeled Species: When the service successfully labels a species, it generates a message to communicate this valuable information. This ensures that the labeled species is available for further processing within our system.

## ML Candidates Service

The ML Candidates Service is tasked with establishing communication with external AI model training services, such as Roboflow.

**External Dependencies**: Roboflow

**Message Handling**:
- New Training Samples are Ready: The service efficiently manages messages indicating that new training samples are prepared and available for use.

**Message Generation**:
- New Trained AI Model: When the service successfully completes the training process and produces a new AI model.

## Camera Feed Engine

The Camera Feed Engine is a specialized service responsible for direct communication with cameras.

**External Dependencies**: Cameras

**Message Handling**:
- New Model is Generated: When a new model is generated, it becomes available for authorized users to upload to the camera. The Camera Feed Engine handles this process of uploading new model.

**Message Generation**:
- New Observation Captured: This event is generated when a camera captures a new observation.
- New Camera Added: When a new camera is registered in the service, the Camera Feed Engine generates an event. This event ensures that the system remains up-to-date with the available camera resources.

# Deployment/Development

The architecture let us scale, maintain, and evolve individual services with ease. However, our approach goes beyond the conventional microservices model.

<p align="center">
    <img src="images/separate.png" alt="image" width="600" height="auto">
</p>


Based on the requirements (the small number of end users) five of our six microservices (excluding the Camera Feed Engine) can be developed and deployed as a cohesive monolith, without compromising the flexibility and scalability inherent in microservices. These services continue to communicate seamlessly through messaging, making it possible to extract and deploy them individually when the need arises e.g. ENS might be extracted due to load increase.

<p align="center">
    <img src="images/monolith.png" alt="image" width="600" height="auto">
</p>

The Camera Feed Engine represents a critical service within our architecture. It is designed to operate independently and is optimized for dynamic scaling based on various factors, such as the number of cameras available and the rates of messages delivered from cameras. This design ensures that this service can efficiently handle varying workloads while remaining separate from the monolithic setup.
