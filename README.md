# Exp-8 -Record-THRESHOLDING
## Reg no: 212224230096
## Name: Iniya E
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.    

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread('IMG.tif')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Original image

plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Use Global thresholding to segment the image

_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
## Output

### Original Image
<img width="192" height="265" alt="image" src="https://github.com/user-attachments/assets/8aa3d630-fb6f-40bb-82cd-b005e8f56a6e" />


### Global Thresholding
<img width="403" height="317" alt="image" src="https://github.com/user-attachments/assets/c4d0265a-28cf-4c52-be58-0272b7efc86e" />


### Adaptive Thresholding
<img width="454" height="308" alt="image" src="https://github.com/user-attachments/assets/0ce92003-7906-4862-b4ea-c827176f34a8" />


### Optimum Global Thesholding using Otsu's Method
<img width="226" height="326" alt="image" src="https://github.com/user-attachments/assets/8e9ced37-24a9-474b-bfe6-55f9b616106c" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
