Parrot Minidrone Competition EMEA 2021
This repository consist of all the work done on the Parrot Mini9drone competition by team ArIES.

DESCRIPTION- The aim of the competition is to get an introduction to Model-Based Design while challenging your peers. We designed a line follower algorithm using Simulink and learn how to model, simulate, and fly a minidrone.

MODEL- The whole model works in the following sequence

IMAGE PROCESSING-
PARROT Image Conversion- converts an image from Y1UY2V format to three-channel RGB format. 
Binarization- Allows us to obtain the Binary image.
Filter- Removes the noise pixels. Makes the contours of the path smoother and continuous.
Borderless-  Removes the objects that touch the image’s borders. During the landing phase, the final portion of the path will not be visible in this image.
Filter_C_Det- detects the final circle when almost centered gives output as “C_DET”
Filter1- Filter1 generates signals corresponding to the increments in position.
Discrete Filter and Gain- Normalization using Delay function and discrete filter. Gains make the movement smoother.
Edge Detection and End Detection-  Edge or End of the line is detection.

PATH PLANNING-
Butterworth 1 Order Filter- To remove noise from the x and y. x and y are further muxed 
Hovering & Tracking- Hovering function gives constant altitude. Tracking gives the x, y using the x, y from path tracking
Switch to Slow Movement- When track ends switches drone to slow  movement from tracking
Switch to Landing- When circle is detected, switches from slow movement to landing
Slow Movement- Gives reduced gain in x, y. Better detection of centre of landing circle
Landing- Diables slow movement. Reduces altitude
Position Signal Generation- Generates reference signal for controller. x, y from all three modes are summed

Praoblems Faced-
1-Initial error of “Out of bound Array Index”
2-Tried to force land the drone at the height of error
3-Later stored the x, y and slowly reduced the z.
