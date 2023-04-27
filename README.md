# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary Packages



### Step2:
Load a image using imread() from cv2 module.


### Step3:
Convert the image to grayscale.


### Step4:
Using Canny operator from cv2,detect the edges of the image



### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates. Display the image.


## Program:
```Python
~~~
Developed by: Vijay.R
Reg. No: 212221230121
~~~

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("img5.jpg",0)
Grimg = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(Grimg)
plt.show()

# Find the edges in the image using canny detector and display
edge = cv2.Canny(Grimg,40,40)
plt.imshow(edge,cmap='gray')
plt.title('Edge image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines = cv2.HoughLinesP(edge,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)

# Display the result
plt.imshow(edge)
plt.axis('off')
plt.show()




```
## Output

### Input image and grayscale image

![img1](https://user-images.githubusercontent.com/94381788/234871706-59b18662-ba46-4434-b14c-640e641b83cd.png)

### Canny Edge detector output

![img2](https://user-images.githubusercontent.com/94381788/234871767-81feecd2-f495-4c77-9487-2e80c6468df6.png)


### Display the result of Hough transform

![img3](https://user-images.githubusercontent.com/94381788/234871838-a42430d6-f7e0-4299-bff7-3c33103e3fd2.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
