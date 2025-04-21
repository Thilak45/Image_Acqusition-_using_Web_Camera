# Image_Acqusition-_using_Web_Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.


## Program:
### Developed By: VELLACHI TILAK
### Register No: 212223240172

## i) Write the frame as JPG file
``` Python
import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```Python
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```Python
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```Python
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()

```

## Output

### i) Write the frame as JPG image

![WhatsApp Image 2025-04-21 at 09 52 32_662bc7e8](https://github.com/user-attachments/assets/57e048a2-029a-45f7-8672-a7fd89d4b76a)


### ii) Display the video
![WhatsApp Image 2025-04-21 at 09 52 32_662bc7e8](https://github.com/user-attachments/assets/105bdc42-865c-4820-8459-4d3fc961679f)



### iii) Display the video by resizing the window


![WhatsApp Image 2025-04-21 at 09 53 01_f6f61ee5](https://github.com/user-attachments/assets/8c683a99-b745-4d94-baba-5e3d0764f017)

### iv) Rotate and display the video

![WhatsApp Image 2025-04-21 at 09 53 19_f9bd5d1a](https://github.com/user-attachments/assets/c6e9669c-0e32-41cf-b04b-6cd2fb4f6fba)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
