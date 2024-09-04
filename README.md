# Pedestrian_Intention_Estimation
The project aims to do an estimation of the pedestrian intention,with binary classification model (cross/not cross) for a prevision of 0,26 second.

The model integrates features from three main branches:

**1)Local Context Branch**: This branch uses a MobileNet-based CNN to extract visual features from 96x96 image frames, followed by a GRU layer to capture temporal dependencies. An attention mechanism is applied to focus on the most relevant visual features.

**2)Pose Branch**: This branch processes pose data using a GRU layer. A ReducedAttentionModule is applied to the pose features with a temperature factor of 2.0 and a scaling factor of the output of 0.5 to reduce their impact in the final decision-making process.

**3)Location trajectory Branch**: This branch handles bounding box coordinates through another GRU layer and applies an attention mechanism to emphasize the most important spatial features.

The outputs from all three branches are concatenated and passed through a final attention layer to fuse the combined features. The model then passes the fused features through a fully connected layer to produce the final classification output, predicting whether a pedestrian is crossing or not.

![image](https://github.com/user-attachments/assets/aeed1dd7-1a41-4c02-8198-b7c6a38825f6)
