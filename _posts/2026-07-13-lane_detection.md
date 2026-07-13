---
title: "Lane detection with Open CV"
categories:
  - car_project
---

```py
import matplotlib.pyplot as plt
import matplotlib.image as mpimg
```

```py
# reading in an image
image = mpimg.imread('solidWhiteCurve.jpg')

# printing out some stats and plotting the image
print('This image is:', type(image), 'with dimensions:', image.shape)
plt.imshow(image)
plt.show()
```

<img width="631" height="549" alt="Image" src="https://github.com/user-attachments/assets/7ede79e2-4422-4a07-9d5e-5cabf7cac393" />

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>