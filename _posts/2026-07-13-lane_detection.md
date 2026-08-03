---
title: "Lane detection with Open CV"
categories:
  - car_project
---

## Introduction
One of the key technologies behind autonomous driving is image processing. In this post, we will use OpenCV in Python to process a road-driving video and generate a new video with the detected lane lines overlaid on it.

Before we start, please note that the code snippets in this post are fragmentary and incomplete. If you would like to see the full source code, visit the GitHub repository [here](https://github.com/enginebeast/vision-project).

## Display the image
<img width="625" height="548" alt="Image" src="https://github.com/user-attachments/assets/cfbb7976-3283-4093-a8b9-0774533499df" />

```py
import matplotlib.pyplot as plt
import matplotlib.image as mpimg
# reading in an image
image = mpimg.imread('solidWhiteCurve.jpg')

# printing out some stats and plotting the image
print('This image is:', type(image), 'with dimensions:', image.shape)
plt.imshow(image)
plt.show()
```

## Convert the image to grayscale
<img width="628" height="554" alt="Image" src="https://github.com/user-attachments/assets/315f7f6c-a1d7-4677-b91e-43fe12e5f8f8" />


To detect the lane lines, we don't need colors. Therefore, we convert the image to grayscale. 

```py
import numpy as np
import cv2
import math
from moviepy import VideoFileClip
from IPython.display import HTML

...

gray_image = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)
```

Although the color image of the displayed result is not gray, you don't need to worry. It is not an error. It is simply the default colormap used by the library. you can display it in 'true' grayscale, but it is not necessary.

## Detect the edges
<img width="629" height="543" alt="Image" src="https://github.com/user-attachments/assets/7fbfe7c7-8db4-4f41-b2b7-9aadf924f41e" />

Next, we need to detect the edges in the image, where the pixel intensity(brightness) changes rapidly. For this, we use the Canny Edge detection algorithm. Fortunately, we don't need to understand the mathematical details for it. OpenCV already implements this algorithm.

```py
cannyed_image = cv2.Canny(gray_image, 100, 200)
```

<img width="626" height="545" alt="Image" src="https://github.com/user-attachments/assets/93ab6006-8960-4d6e-bd40-23902918350e" />

<img width="626" height="543" alt="Image" src="https://github.com/user-attachments/assets/a374ac3f-a69d-49f3-ae76-05f8aef48dde" />

<img width="626" height="541" alt="Image" src="https://github.com/user-attachments/assets/1bc1f923-ca45-4237-83d6-cf0c0923308b" />

## Apply to a video
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe
    src="https://www.youtube.com/embed/3zE010sjwDw"
    title="YouTube video player"
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

You can download the unedited video 
[here](https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4).

## Conclusion
In this post, we generate the video with detected lane lines overlaid on it. However, real self-driving car must detect lane lines and make driving decision on them in real time.

We will implement this process by real self-drving mini-car built with Raspberry Pi.

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>
<https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4>