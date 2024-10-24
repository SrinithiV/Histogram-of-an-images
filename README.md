# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program:
# Developed By: 212222110046
# Register Number: SRINITHI V
### Input Grayscale Image and Color Image
```py
import cv2
import matplotlib.pyplot as plt
img1=cv2.imread('gray.jpg')
img2=cv2.imread('color.jpg')
gray_image = cv2.resize(img1,(500,500))
color_image = cv2.resize(img2,(500,500))
cv2.imshow("Gray image",gray_image)
cv2.imshow("color image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Histogram of Grayscale Image
```py
import numpy as np
gray_image=cv2.imread('gray.jpg')
import matplotlib.pyplot as plt 
gray_hist=cv2.calcHist(gray_image,[0],None,[255],[0,255])
plt.figure(figsize=(10,6))
plt.subplot(1,2,1)
plt.imshow(gray_image)
plt.subplot(1,2,2)
plt.title("Histogram")
plt.xlabel("Grayscale value")
plt.ylabel("pixel count")
plt.stem(gray_hist)
plt.show()
```

### Histogram of any channel of Color Image
```py
import numpy as np
color_image=cv2.imread('color.jpg')
color_img=cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB)
import matplotlib.pyplot as plt 
color_hist=cv2.calcHist(color_img,[0],None,[255],[0,255])
plt.figure(figsize=(8,4))
plt.subplot(1,2,1)
plt.imshow(color_img)
plt.subplot(1,2,2)
plt.title("Histogram")
plt.xlabel("Colorscale value")
plt.ylabel("pixel count")
plt.stem(color_hist)
plt.show()
```

### Histogram Equalization of Grayscale Image
```py
import cv2
img1= cv2.imread("gray.jpg",0)
gray_image = cv2.resize(img1,(500,500))
cv2.imshow('Grey Scale Image',gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:
### Input Grayscale Image and Color Image
![Screenshot 2024-10-24 112053](https://github.com/user-attachments/assets/f2e83303-ba2d-4e30-a551-fc6c9f56fda8)

### Histogram of Grayscale Image
![Screenshot 2024-10-24 112350](https://github.com/user-attachments/assets/f0be45c6-eba4-41fe-8f67-f017a810ccc7)

### Histogram of any channel of Color Image
![Screenshot 2024-10-24 112401](https://github.com/user-attachments/assets/7eb30e2b-068c-4534-a418-72df19c54f78)

### Histogram Equalization of Grayscale Image
![Screenshot 2024-10-24 112753](https://github.com/user-attachments/assets/8f1ccc7a-fb1c-40b1-86ef-24ef48fb2c2b)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
