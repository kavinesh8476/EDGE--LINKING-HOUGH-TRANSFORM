# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.
<br>

### Step2:
Find the edges in the image using canny detector and display.
<br>

### Step3:
Detect points that form a line using HoughLinesP.
<br>

### Step4:
Draw lines on the image.
<br>

### Step5:
Display the result.
<br>


## Program:
```
Developed by:Kavinesh M
Register Number :212222230064
```

# Read image and convert it to grayscale image
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("d.jpg",0)
img_c=cv2.imread("d.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

```


# Find the edges in the image using canny detector and display
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

```


# Detect points that form a line using HoughLinesP
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

```


# Draw lines on the image
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)

```


# Display the result
```python
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

### Input image and grayscale image
<br>

![image](https://github.com/kavinesh8476/EDGE--LINKING-HOUGH-TRANSFORM/assets/118466561/11e3674b-0379-4bcb-b79d-8338ec111eb2)

<br>

### Canny Edge detector output
<br>

![image](https://github.com/kavinesh8476/EDGE--LINKING-HOUGH-TRANSFORM/assets/118466561/43b7c575-16a3-43b1-b3d5-1489acf09702)

<br>



### Display the result of Hough transform
<br>

![image](https://github.com/kavinesh8476/EDGE--LINKING-HOUGH-TRANSFORM/assets/118466561/b2b427c8-c784-400e-9cae-e9826944e4bb)

<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
