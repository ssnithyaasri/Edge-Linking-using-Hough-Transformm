# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program :
##  Name : NITHYAA SRI S S
## Register Number : 212222230100

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('t.JPG')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))

# Input Image and Grayscale Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')

```
## Output
### Input image and grayscale image
![image](https://github.com/user-attachments/assets/ebad8a78-ab3c-47ad-a55f-c51cea493384)
![image](https://github.com/user-attachments/assets/0a35f176-752d-47c8-bd32-fc0868f5a76b)



### Canny Edge detector output
```
# Canny Edge Detection Output
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')

```
## Output
![image](https://github.com/user-attachments/assets/f3ee1beb-6897-48b8-a441-1f63ae1d3bf6)

### Display the result of Hough transform
# Hough Transform Result

plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')

# Display all results
plt.show()
![image](https://github.com/user-attachments/assets/ffce0abd-0bf5-40d1-bf3d-3b6ff34817fb)

# Result :
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
