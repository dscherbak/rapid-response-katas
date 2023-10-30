# Mobile Video/Image Processing

## Context:
In order to easily share observation footage and images, a user needs to be able to process them on a mobile device. This will allow us to reduce the size of the files and make them easier to share. These video/image editing features include tasks such as trimming, cropping, rotating, and frame extraction.

## Decision:
To implement video editing in our React Native application for both iOS and Android, we have decided to use the "react-native-video" library for video playback and the "react-native-video-processing" library for video editing, "react-native-image-picker" and "react-native-image-resizer" for image editing.

## Rationale:

### Cross-Platform Compatibility:
Both "react-native-video" and "react-native-video-processing" libraries are compatible with both iOS and Android platforms, ensuring consistent functionality and a single codebase for video editing features.

### Feature-Rich:
"react-native-video" provides powerful video playback capabilities, while "react-native-video-processing" offers a wide range of video editing features, including trimming, cropping, rotating, and applying filters. This combination allows us to implement a broad set of video editing functionalities.

## Consequences:
By using "react-native-video" and "react-native-image-picker"  in combination with other supporting libraries, we anticipate efficient image selection and image manipulation capabilities, resulting in a user-friendly and feature-rich photo processing experience. However, we must ensure that all libraries remain actively maintained and continue to meet our evolving project needs.

## Status:
Proposed
