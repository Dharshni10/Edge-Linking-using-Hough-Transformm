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
### Name : Dharshni V M
### Register Number : 212223240029
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('pic.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image 
![input](https://github.com/user-attachments/assets/63e4bd40-0182-4bf2-8fb7-625ccc31ad22)

### Grayscale image
![gray](https://github.com/user-attachments/assets/71453900-3460-4730-8210-4b9e9815412b)

### Canny Edge detector output
![canny](https://github.com/user-attachments/assets/3deb5ca8-c11c-48ab-99d2-32c5c37c9636)

### Display the result of Hough transform
![hough](https://github.com/user-attachments/assets/1d3687f5-3741-4904-804e-621e79450ac5)

## Result
Thus the grayscale image , canny edge detector and hence we had displayed the result of hough transform
