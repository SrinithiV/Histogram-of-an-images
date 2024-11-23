## Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread().

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program:
## Developed By: 212222110046
## Register Number: SRINITHI V
### Getting the input grayscale image and displaying it:
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
gray_image = cv2.imread('Dog.png', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/e30d6a0d-cedf-4c43-9937-f09396508589)

### Histogram of Grayscale Image:
```py
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/9b25091e-5b86-4318-93b2-93f7ced789e1)

### Histogram of Equalized Grayscale Image:
```py
equalized_gray_image = cv2.equalizeHist(gray_image)
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/59ec3ed5-6fcd-4ad3-9802-a3568ffd703e)

### Enhanced Grayscale Image:
```py
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/7c3a47b6-763f-46b0-ad3f-3cbbafcd3e3b)

### Getting the input Color image and displaying it:
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
color_image = cv2.imread('cat.png')
plt.title("Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/7f122103-6d7d-4ac4-a538-15260781b420)

### Histogram of Color Image:
```py
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
plt.title("Histogram of Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/781afae3-a735-4335-a00d-e79d2ca0add3)

### Histogram of Equalized Color Image:
```py
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])
plt.title("Histogram of Equalized Color Image")
plt.hist(equalized_color_image.ravel(), bins=256, color='blue', alpha=0.6)
plt.xlim(0, 255)
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/8a7c81bc-de7a-4fe0-9399-be8ba75faf7a)

### Enhanced Color Image:
```py
plt.title("Enhanced Color Image")
plt.imshow(equalized_color_image, cmap='gray')
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/2f83b313-d00c-4d0b-a5dd-b128a22dd6e6)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
