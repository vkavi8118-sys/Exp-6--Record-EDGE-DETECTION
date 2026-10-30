# Exp-6--Record-EDGE-DETECTION
## NAME : KAVINAYA V
## REGISTER NO : 212225230133
## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('ex1 image.jpeg')  # Replace with your image path
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

## Output

### Input Image 
<img width="762" height="610" alt="Screenshot 2026-10-30 175536" src="https://github.com/user-attachments/assets/1917e785-f8b0-44a3-ad6d-297265118c79" />

### 1. Sobel Edge Detector
<img width="762" height="608" alt="Screenshot 2026-10-30 175549" src="https://github.com/user-attachments/assets/186a98eb-e448-4816-828f-f00f459e17ae" />

### 2. Laplacian Edge Detector
<img width="762" height="608" alt="Screenshot 2026-10-30 175751" src="https://github.com/user-attachments/assets/6a9ed696-0656-4eb8-9032-16e4b62ce947" />

### 3. Canny Edge Detector
<img width="763" height="612" alt="Screenshot 2026-10-30 175805" src="https://github.com/user-attachments/assets/5088dde4-06c0-4cc1-b58c-e4c410a5314c" />

## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
