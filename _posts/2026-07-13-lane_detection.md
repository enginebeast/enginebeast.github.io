---
title: "Lane detection with Open CV"
categories:
  - car_project
---

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
<img width="625" height="548" alt="Image" src="https://github.com/user-attachments/assets/cfbb7976-3283-4093-a8b9-0774533499df" />

<img width="628" height="554" alt="Image" src="https://github.com/user-attachments/assets/315f7f6c-a1d7-4677-b91e-43fe12e5f8f8" />

<img width="629" height="543" alt="Image" src="https://github.com/user-attachments/assets/7fbfe7c7-8db4-4f41-b2b7-9aadf924f41e" />

<img width="626" height="545" alt="Image" src="https://github.com/user-attachments/assets/93ab6006-8960-4d6e-bd40-23902918350e" />

<img width="626" height="543" alt="Image" src="https://github.com/user-attachments/assets/a374ac3f-a69d-49f3-ae76-05f8aef48dde" />

<img width="626" height="541" alt="Image" src="https://github.com/user-attachments/assets/1bc1f923-ca45-4237-83d6-cf0c0923308b" />

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

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>