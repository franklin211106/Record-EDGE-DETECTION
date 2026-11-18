# Exp-6--Record-EDGE-DETECTION

## Aim:
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required:

Anaconda – Python 3.7    
Jupyter Notebook / VS Code    
OpenCV (cv2)    
NumPy    
Matplotlib    

## Algorithm:

Step 1:
Import all the necessary modules for the program.

Step 2:
Load an image using cv2.imread().

Step 3:
Convert the image to grayscale.

Step 4:
Apply Sobel operator using OpenCV to detect edges.

Step 5:
Apply Prewitt operator using custom kernels.

Step 6:
Apply Roberts operator using custom kernels.

Step 7:
Apply Laplacian operator using OpenCV.

Step 8:
Apply Canny edge detector using OpenCV.

Step 9:
Display all edge-detected images for comparison.

## Program:

### Developed By
### Name: FRANKLIN F
### Reg.No: 212224240041

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('WhatsApp Image 2026-10-24 at 3.32.56 PM.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

## Output:

### Original image

<img width="367" height="501" alt="image" src="https://github.com/user-attachments/assets/c2d136f1-40b5-47d4-9739-97e6282b0700" />


### Sobel Edge Detector

Detects edges in horizontal and vertical directions    
Produces gradient-based edge map

<img width="390" height="522" alt="image" src="https://github.com/user-attachments/assets/be459d99-8036-413b-931a-40140456f7cc" />


### Laplacian Edge Detector

Detects edges using second-order derivatives    
Highlights rapid intensity changes

<img width="402" height="511" alt="image" src="https://github.com/user-attachments/assets/ed73b2c2-4d8f-4ce9-96a2-2dcfe25c1b14" />


### Canny Edge Detector

Multi-stage edge detection    
Produces clean and thin edges

<img width="375" height="500" alt="image" src="https://github.com/user-attachments/assets/2b2d37f0-875e-481e-bd88-60b697ab1c59" />


## Result:

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
