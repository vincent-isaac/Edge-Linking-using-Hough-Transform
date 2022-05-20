# Edge-Linking-using-Hough-Transform
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
from cv2 import cvtColor
image=cv2.imread("OIP.jpg")
cv2.imshow("ORIGINAL",image)

gray=cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)

plt.figure(1)
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image)
plt.title('gray')
plt.axis('off')


# Find the edges in the image using canny detector and display

edges = cv2.Canny(image, 120, 150)
plt.imshow(edges)
plt.title('EDGES')
plt.axis('off')

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edges,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)


# Draw lines on the image

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,0,205),2)

# Display the result

plt.imshow(image)
plt.title('HOUGH')
plt.axis('off')


```
## Output

### Input image and grayscale image
![Capture15](https://user-images.githubusercontent.com/75234588/169475703-a53b0574-9417-49c5-b0b3-5be5df25343d.PNG)
![Capture16](https://user-images.githubusercontent.com/75234588/169475717-0e3f6327-f9fa-49d1-b3b0-250c4f653f00.PNG)



### Canny Edge detector output
![Capture17](https://user-images.githubusercontent.com/75234588/169475760-dfc01882-974a-4836-9bd4-1784c8d53ca0.PNG)

### Display the result of Hough transform
![Capture18](https://user-images.githubusercontent.com/75234588/169475791-0fcdb12a-db2b-48d5-878f-4a26a1285d00.PNG)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
