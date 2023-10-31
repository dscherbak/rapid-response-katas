# Wildlife Watcher System
overview...

## Glossary
1. **Camera** - a Wildlife.ai device that records animals and uses AI to identify them.
2. **AI Model** - a result of Machine Learning (ML) using services like TensorFlow, Roboflow, etc.
3. **User** - biologists and nature enthusiasts.
4. **Admin** - a user with extended permissions to camera management (like configuring camera settings, and uploading AI model/firmware).
5. **Observation** - an event produced by the Camera of the captured movement.
6. **Training Sample** - a video and(or) photo labeled and selected by Admin for ML.

## Functional requirements
### Short-term
  #### Camera:
  - The camera should be capable of capturing images or videos of animals.
  - The camera should be able to send a small event message with a photo of observed species.

  #### Users:
  - Users should be able to create accounts and log in securely.
  - Allow users to configure camera settings.
  - Allow users to publish frames of observation to third-party services for experts to help with
    the identification of the species (for example, iNaturalist).
  - Allow users to train AI models using training samples.
  - Allow users to export an observation event into the Camtrap DP data exchange format.

  #### Platform:
  - Support integrations with common camera trap labeling platforms
    (Wildlife Insights, TrapTagger, or Trapper)
  - Focus on the scale of dozens of cameras and hundreds of users.
  - Consider open-source software and tools to minimize licensing costs.
  - Design the system to handle a potential increase in users and data as the user base grows.

### Mid-term
  #### Platform
  - Store user-captured images and videos securely.
  - Integrate with mapping services to show the location of identified animals.
  - Provide information on animal habitats.
  - Store identification results locally (on the camera) and synchronize when online.

### Long-term
  #### Platform
  - Implement a community forum or social features to connect enthusiasts.
