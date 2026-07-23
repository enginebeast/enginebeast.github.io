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

You can download the video 
[here](https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4).

## Conclusion
글의 프로그램은 기존의 영상을 처리해서 도로 선을 인지한 새로운 영상을 만들어낸 것이다. 하지만 실제 자율 주행 자동차에서는 도로 선을 매 순간마다 인지하고 그에 따라 판단을 하는 과정을 반복하는 것이 필요할 것이다.

이 과정은 실제로 라즈베리파이를 통해 만든 차체를 통해 해보도록 하겠다.

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>
<https://github.com/udacity/CarND-LaneLines-P1/blob/master/test_videos/solidWhiteRight.mp4>