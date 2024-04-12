# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
### Step 2:
Use cv2.imread to read the video or image
### Step 3:
Use cv2.imwrite to save the image
### Step 4:
Use cv2.imshow to show the video
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
```
Developed By: Karthick P
Register No: 212222100021
```
## i) Write the frame as JPG file
```python
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("Mukilan.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('212222230167',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230167',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230167',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![WhatsApp Image 2024-02-29 at 17 53 14_84c1fba1](https://github.com/Vasanthamukilan/Image_Acqusition-_using_Web_Camera/assets/119559694/0e0ba178-4216-4ff1-b183-705b1c3fe3d8)

### ii) Display the video
![WhatsApp Image 2024-02-29 at 17 57 49_e6c7dda4](https://github.com/Vasanthamukilan/Image_Acqusition-_using_Web_Camera/assets/119559694/d1cf627c-c8bd-4f2a-8aa3-32d928f90bea)

### iii) Display the video by resizing the window
![WhatsApp Image 2024-02-29 at 17 53 14_adbdb38b](https://github.com/Vasanthamukilan/Image_Acqusition-_using_Web_Camera/assets/119559694/024353cf-f2ad-4f9c-a31a-b9ab3388c526)

### iv) Rotate and display the video
![WhatsApp Image 2024-02-29 at 17 56 31_c8b644c2](https://github.com/Vasanthamukilan/Image_Acqusition-_using_Web_Camera/assets/119559694/0691ca31-f850-418c-974b-036b7c7a711c)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
