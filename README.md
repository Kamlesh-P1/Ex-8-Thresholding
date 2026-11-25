# Image Segmentation Using Thresholding Techniques in OpenCV

# Developed By
# Name: KAMLESH P
# Register No: 212225240067

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

##  Software Used
- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

Select a fixed threshold value.
Apply thresholding to separate foreground and background pixels.
Display the thresholded image.

### Step 5: Adaptive Thresholding

Compute threshold values for small regions of the image.
Apply Adaptive Mean Thresholding.
Apply Adaptive Gaussian Thresholding.
Display the segmented images.

### Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.
Apply Otsu's thresholding technique.
Display the segmented image.

### Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program
~~~python


import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('1.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")
plt.axis('off')

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

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

~~~

## output 

Original Image

<img width="174" height="245" alt="Screenshot 2026-11-25 222711" src="https://github.com/user-attachments/assets/7a58c984-214e-4f1c-8618-967641dedfcc" />



Thresholding

<img width="578" height="549" alt="image" src="https://github.com/user-attachments/assets/9318c131-b528-4bc0-9be6-dc3ff5b64c59" />



## Result

Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
