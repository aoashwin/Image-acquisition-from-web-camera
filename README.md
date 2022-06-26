## Ex no: 2
## Date: 8/4/2022
# <p align="center"> Image Acquisition from Web Camera
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
<br>Use VideoCapture(0) to access web camera

### Step 2:
<br>Use imread to read the video or image

### Step 3:
<br>Use imwrite to save the image

### Step 4:
<br>Use imshow to show the video

### Step 5:
<br>End the program and close the output video windows by pressing 'q'

## Program:
``` Python
### Developed By: ASHWIN A O
### Register No: 212220230005

## i) Write the frame as JPG file
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("KB.jpg",frame)
cap.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
ret,frame=cap.read()
cv2.imshow('frame',frame)
if cv2.waitKey(1)==ord('q'):
break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2,:width//2]=smaller_frame
image[height//2: , :width//2]=smaller_frame
image[:height//2,width//2:]= smaller_frame
image[height//2:,width//2:]=smaller_frame
cv2.imshow('frame',image)
if cv2.waitKey(1)==ord('q'):
break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2
image[height//2: , :width//2]=smaller_frame
image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv
image[height//2:,width//2:]=smaller_frame
cv2.imshow('frame',image)
if cv2.waitKey(1)==ord('q'):
break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
</br>![DIP2 - 1](https://user-images.githubusercontent.com/75235601/162605582-50d61e11-7d4d-4e02-ae46-5b2cc1baeade.jpeg)


### ii) Display the video
</br>![DIP2 - 2](https://user-images.githubusercontent.com/75235601/162605589-7708e00e-ebe1-4ab4-a127-faa0d72c0a0b.jpeg)


### iii) Display the video by resizing the window
</br>![DIP2 - 3](https://user-images.githubusercontent.com/75235601/162605590-609f6db7-e12a-4800-a34a-d7ecf75f5c4a.jpeg)


### iv) Rotate and display the video
</br>![DIP2 - 4](https://user-images.githubusercontent.com/75235601/162605594-f1c49831-894d-409c-a51b-a8c0e98d887f.jpeg)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
