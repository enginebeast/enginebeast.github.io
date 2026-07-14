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

<img width="631" height="549" alt="Image" src="https://github.com/user-attachments/assets/7ede79e2-4422-4a07-9d5e-5cabf7cac393" />

```py
import matplotlib.pyplot as plt
import matplotlib.image as mpimg
import numpy as np
import cv2
from numpy import imag

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

# reading in an image
image = mpimg.imread('solidWhiteCurve.jpg')

# printing out some stats and plotting the image
print('This image is:', type(image), 'with dimensions:', image.shape)

height = image.shape[0]
width = image.shape[1]

region_of_interest_vertices = [
    (0, height),
    (width / 2, height / 2),
    (width, height),
]

cropped_image = region_of_interest(
    image,
    np.array([region_of_interest_vertices], np.int32),
)
plt.figure()

plt.imshow(cropped_image)
plt.show()
```

<img width="621" height="549" alt="Image" src="https://github.com/user-attachments/assets/4d9d595f-4039-4a84-88bd-7c470b8f21a4" />

<img width="624" height="549" alt="Image" src="https://github.com/user-attachments/assets/2f3ba2de-2d66-434e-94f9-bfd66aa233d2" />

<img width="626" height="545" alt="Image" src="https://github.com/user-attachments/assets/283fce96-d59b-4999-9dae-6c4693ea8c04" />

## Source
<https://medium.com/@mrhwick/simple-lane-detection-with-opencv-bfeb6ae54ec0>