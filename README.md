# Image_Acqusition-_using_Web_Camera

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Write the frame as JPG 

### Step 2:
Display the video 

### Step 3:
Display the video by resizing the window

### Step 4:
Rotate and display the video

## Program:
### Developed By:R.SUROHAAMAN
### Register No:212222103003S


## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

import cv2

videoCaptureObject = cv2.VideoCapture(0)
max_frames = 4  # Maximum number of frames to capture
frame_count = 0
while frame_count < max_frames:
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"img_{frame_count}.jpeg", frame)
    frame_count += 1

videoCaptureObject.release()
cv2.destroyAllWindows()

```
## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

```

## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![WhatsApp Image 2024-03-01 at 12 32 40_5669acb0](https://github.com/surothaaman/Image_Acqusition-_using_Web_Camera/assets/133313653/7fcd4648-7998-4ff6-a29d-5472d53f464a)



### ii) Display the video
![Screenshot 2024-03-01 122702](https://github.com/surothaaman/Image_Acqusition-_using_Web_Camera/assets/133313653/b53122df-dee0-430b-958d-b5de1d49c809)



### iii) Display the video by resizing the window
![Screenshot 2024-03-01 122829](https://github.com/surothaaman/Image_Acqusition-_using_Web_Camera/assets/133313653/8f80438a-c0b9-4509-a8c5-39e212006240)


### iv) Rotate and display the video
![Screenshot 2024-03-01 122906](https://github.com/surothaaman/Image_Acqusition-_using_Web_Camera/assets/133313653/74e75885-7c86-4824-922f-f4f240c97d70)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
