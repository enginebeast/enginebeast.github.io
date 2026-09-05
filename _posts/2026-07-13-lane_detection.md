---
title: "Lane Detection with Open CV"
categories:
  - car_project
---

## Introduction
One of the key technologies behind self-driving is image processing. In this post, we will use OpenCV in Python to process a road-driving video and generate a new video with the detected lane lines overlaid on it.

Before we start, please note that the code snippets in this post are fragmentary and incomplete. If you would like to see the full source code, visit the GitHub repository [here](https://github.com/enginebeast/vision-project).

## Display the Image
<img width="625" height="548" alt="Image" src="https://github.com/user-attachments/assets/cfbb7976-3283-4093-a8b9-0774533499df" />

First, we need to display the image so that we can check the result of each processing step. The following code allows us to do this.

```py
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

# reading in an image
image = mpimg.imread('solidWhiteCurve.jpg')

# printing out some stats and plotting the image
plt.imshow(image)
plt.show()
```

## Convert the Image to Grayscale
<img width="628" height="554" alt="Image" src="https://github.com/user-attachments/assets/315f7f6c-a1d7-4677-b91e-43fe12e5f8f8" />


To detect the lane lines, color is unnecessary information for calculation. This is because the algorithm we use in the next step only uses differences in brightness. Therefore, we convert the image to grayscale.

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

## Detect the Edges
<img width="629" height="543" alt="Image" src="https://github.com/user-attachments/assets/7fbfe7c7-8db4-4f41-b2b7-9aadf924f41e" />

Next, we need to detect the edges in the image, where the pixel intensity(brightness) changes rapidly. For this, we use the Canny Edge detection algorithm. Fortunately, we don't need to understand the mathematical details for it. OpenCV already implements this algorithm.

```py
cannyed_image = cv2.Canny(gray_image, 100, 200)
```

## Crop the Image to a Triangular Region
<img width="626" height="545" alt="Image" src="https://github.com/user-attachments/assets/93ab6006-8960-4d6e-bd40-23902918350e" />
Now, we crop the image to a triangle region.

```py
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

import numpy as np
import cv2

def region_of_interest(img, vertices):
    # Define a blank matrix that matches the image height/width.
    mask = np.zeros_like(img)
    # Retrieve the number of color channels of the image.
    channel_count = img.shape[2]
    # Create a match color with the same color channel counts.
    match_mask_color = (255,) * channel_count
      
    # Fill inside the polygon
    cv2.fillPoly(mask, vertices, match_mask_color)
    
    # Returning the image only where mask pixels match
    masked_image = cv2.bitwise_and(img, mask)
    return masked_image

image = mpimg.imread('solidWhiteCurve.jpg')

height = image.shape[0]
width = image.shape[1]

region_of_interest_vertices = [
    (0, height),
    (width / 2, height / 2),
    (width, height),
]
image = mpimg.imread('solidWhiteCurve.jpg')
cropped_image = region_of_interest(
    cannyed_image,
    np.array([region_of_interest_vertices], np.int32),
)
```

Here, you should not misunderstand this as an absolute standard for image detection. It is just an arbitrary choice.

## Draw Red Lines over the Lane Markings
<img width="626" height="543" alt="Image" src="https://github.com/user-attachments/assets/a374ac3f-a69d-49f3-ae76-05f8aef48dde" />

## Connect the Line Segments
<img width="626" height="541" alt="Image" src="https://github.com/user-attachments/assets/1bc1f923-ca45-4237-83d6-cf0c0923308b" />

## Apply to a Video
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
In this step, we apply the what we learned to a video.
You can download the unedited video 
[here](https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4).

## Conclusion
In this post, we generate the video with detected lane lines overlaid on it. However, real self-driving car must detect lane lines and make driving decision on them in real time.

We will implement this process by real self-drving mini-car built with Raspberry Pi.

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>

<https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4>