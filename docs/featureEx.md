# Feature Extraction

```
import cv2
import numpy as np

img = cv2.imread('home.jpg')

sift = cv2.SIFT()
kp = sift.detect(img,None)

img=cv2.drawKeypoints(img,kp)

cv2.imwrite('sift_keypoints.jpg',img)
```