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
<br>Import the cv2 and numpy package.

### Step 2:
<br>Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
<br>Write the image using imwrite().

### Step 4:
<br>Display the frame using the imshow().
   
### Step 5:
<br>Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
``` Python
### Developed By: THARUN SRIDHAR 
### Register No: 212223230230

## i) Write the frame as JPG file
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```




## ii) Display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```



## iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```



## iv) Rotate and display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```


```
## Output

### i) Write the frame as JPG image
</br>
</br>
<img width="512" height="409" alt="image" src="https://github.com/user-attachments/assets/487b0fc2-a315-429d-8c90-8d5abcd4816a" />

### ii) Display the video
</br>
</br>
<img width="512" height="389" alt="image" src="https://github.com/user-attachments/assets/98f51295-02e5-4a0f-bd49-b7b21b12c30c" />


### iii) Display the video by resizing the window
</br>
</br>
<img width="266" height="389" alt="image" src="https://github.com/user-attachments/assets/918c263f-a591-47e9-a23b-28ac6ac47857" />

### iv) Rotate and display the video
</br>
</br>
<img width="297" height="389" alt="image" src="https://github.com/user-attachments/assets/17ef9d74-7293-4812-91fb-b22cb599b0bd" />





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
