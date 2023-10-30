# Network Physical Constraints

In our investigation, we discovered the limitations of both LoRaWAN and 3G network connections for data transmission, as summarized in the table below:

| Network   | Minimum   | Maximum   |
| --------- | --------- | --------- |
| 3G        | 300 kbps  | 2 Mbps    |
| LoRaWAN   | 1 kbps    | 50 kbps   |

We also calculated the size of a ten-second 720p video, which is approximately 2.2 MB, assuming a rate of 227 KB per second. Even with a 3G connection, it would take around 55 seconds (considering the worst-case 3G upload speed of 300 kbps) to transmit the video from the camera. These numbers were found to be unacceptable for meeting the system's requirements.

On the other hand, a compressed low-quality 720p image is about 30 KB in size. Additional attributes, such as camera ID, species, time, temperature, etc., may add an extra 1 KB, resulting in a total message size of around 31 KB.

It's important to note that the LoRaWAN package size is limited to 256 bytes, meaning a 31 KB message would need to be divided into approximately 125 packets.

Here are the estimated transmission times for sending this message by LoRaWAN network:

- On a low-quality network with a transmission rate of 1 kbps, the transmission time for each message would be around 240 seconds.
- On a mid-quality network with a transmission rate of 20 kbps, it would take approximately 13 seconds to transmit the message.

In contrast, for a 3G network, even in the worst-case scenario, it would take up to 2 seconds to transmit such a message with an image.

Based on our research, we have decided to send images instead of videos. This decision is based on our belief that it is crucial for the user to see what has been recorded. When the users have a visual of a captured species, they can make decisions and act based on that information.

Nevertheless, if the camera identifies the species it should be possible to send an event without an image (this feature should be configured per camera).
