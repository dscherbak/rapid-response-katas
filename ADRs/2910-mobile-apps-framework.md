# Mobile Apps Framework

## Context:
The Wildlife Watcher project is planned to be an open-source project.
The resources available for the project are limited. Therefore, the decision regarding the choice of technology and framework for building this client app is crucial.

## Decision:
After evaluating various options and considering the project's requirements, we have decided to implement the client application for both iOS and Android using **React Native**.

## Rationale:

### Cross-Platform Compatibility:

React Native is known for its ability to create cross-platform applications with a single codebase. This approach allows us to share a significant portion of the code between the iOS and Android versions of the client app, reducing development effort, time, and potential inconsistencies between platforms.

### Cost-Effectiveness:

Developing and maintaining separate native apps for iOS and Android can be resource-intensive and expensive. React Native helps us maximize development resources by sharing code and reducing the need for platform-specific development.


## Consequences:

By choosing React Native for our iOS and Android client app, we anticipate reaping the benefits of cost-effectiveness, cross-platform compatibility, and an efficient development process. However, this decision does come with a potential learning curve for developers less familiar with React Native and its nuances.

## Status:
Approved
