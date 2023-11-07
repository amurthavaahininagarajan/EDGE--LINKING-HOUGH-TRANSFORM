# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary packages.
<br>

### Step2:
Read the image
<br>

### Step3:
Convert the image to greyscale.
<br>

### Step4:
Using Canny operator from cv2,detect the edges of the image.
<br>

### Step5:
Detect line co-ordinates for every points in the images. Draw the lines on the found co-ordinates and display the image.
<br>


## Program:

###  Read image and convert it to grayscale image
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('1.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)
~~~


# Find the edges in the image using canny detector and display
~~~
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
~~~


# Detect points that form a line using HoughLinesP
~~~
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
~~~


# Draw lines on the image
~~~
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)
~~~

# Display the result
~~~
plt.imshow(edges1)
~~~


## Output

### Input image and grayscale image
![1](https://user-images.githubusercontent.com/94980741/169020246-6a748ffc-5377-40c8-9734-d8d5f8ce3147.png)


### Canny Edge detector output
![2](https://user-images.githubusercontent.com/94980741/169020313-f1a90c54-24d0-4264-aca7-a0f101c41bf5.png)



### Display the result of Hough transform
![3](https://user-images.githubusercontent.com/94980741/169020337-c62a63f6-0d2f-42a1-b649-bb89f5da2bb0.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
