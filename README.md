# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:

```
Developed By : SWATHI D
Register Number : 212222230154
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('L.jpeg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output


### Input image and grayscale image


![Screenshot 2024-10-02 144307](https://github.com/user-attachments/assets/2f3dd905-97ae-420a-84c7-f13f1780ff42)


![Screenshot 2024-10-02 144428](https://github.com/user-attachments/assets/271aa432-6525-407c-85a1-b9e54625d887)


### Canny Edge detector output


![Screenshot 2024-10-02 144439](https://github.com/user-attachments/assets/6092dab0-9be0-4a9c-8571-d699551ef69b)


### Display the result of the Hough transform



![Screenshot 2024-10-02 144449](https://github.com/user-attachments/assets/8585db37-c41a-414b-ac58-092658d5b79d)


## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
