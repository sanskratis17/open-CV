# open-CV
## **1. Changing Image's Color Profile**
import cv2
from google.colab.patches import cv2_imshow

#colorful image - 3 channels
image = cv2.imread('minion.jpg')
cv2_imshow(image)
print(image.shape)

#grayscale image
gray = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2_imshow(gray)
print(gray.shape)

#HSV Image
HSV = cv2.cvtColor(image,cv2.COLOR_BGR2HSV)
cv2_imshow(HSV)
print(HSV.shape)
## **2. EDGE Detection**
import cv2
from google.colab.patches import cv2_imshow
import numpy as np

image = cv2.imread('minion.jpg')
#cv2_imshow(image)

gray = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
canny_image = cv2.Canny(gray,150,200)
cv2_imshow(canny_image)

#Erosion & Dilation
kernel = np.ones((2,2), np.uint8)
erode_image = cv2.erode(canny_image,kernel, iterations=1)
cv2_imshow(erode_image)
