# Access permissions to cameras

## Context
Users with admin privileges need to be able to access the cameras in order to upload new AI models, update camera settings, and switch them on/off.

## Decision
Cameras to user relations will be stored in the Identity Service database. Permissions will be built into JWT tokens. The Camera Feed Engine will check the permissions of the user before allowing access to the camera.

## Rationale
This decision is based on the following factors:

### Performance:
The Camera Feed Engine will be able to quickly check the permissions of the user by decoding the JWT token. This will allow the Camera Feed Service to quickly determine whether the user is authorized to access the camera.

## Consequences
The decision to use JWT tokens to store camera permissions has several consequences:

* The Identity Service will need to store the camera permissions for each user.
* The Camera Feed Engine will need to decode the JWT token to determine whether the user is authorized to access the camera.

## Status
Proposed
