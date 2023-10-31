# Machine learning process

## Context:

Training a machine learning model for an AI camera is critically important because it is the foundation of the system's ability to recognize and identify animals accurately.
The initial AI model deployed in the AI camera may have limited accuracy and recognition capabilities. Machine learning models require training on extensive and diverse datasets to learn and improve their ability to identify animals effectively. Through ongoing training, the model can continually refine its understanding of various animal species, improving its accuracy in real-world scenarios.
Since the ML on a device is not available because of memory restrictions, it needs to be performed inside or outside of the system.

## Decision:

Based on our research, we've decided to have a dedicated service for the machine learning process - ML candidates service.
The observations that have been initially unknown to a camera and then were labeled (by a user or third-party tool) will end up in the ML candidates service.
Also, a user can select media files to be sent as training samples. 
The ML candidates service will be some sort of ordered queued training samples. 
The admin users will be able to configure which samples will be extracted for the ML process.
The ML process is currently designed to be external to the system.

## Consequences:

Having ML candidates service is a crucial part of the system. It's a centralized hub for all the observation events that are potentially training samples.

## Status:

Approved
