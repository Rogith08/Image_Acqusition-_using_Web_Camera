# Experiment 2-Image Acquisition using Web Camera
# Name: ROGITH. K
# Reg No: 212223110042
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used:
Anaconda - Python 3.7

## Algorithm:
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
``` Python
### Developed By: ROGITH. K
### Register No: 212223110042

## i) Write the frame as JPG file
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

## ii) Display the video
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

## iii) Display the video by resizing the window
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

## iv) Rotate and display the video
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
## Output:

### i) Write the frame as JPG image
<img width="621" height="492" alt="Screenshot 2025-09-22 114858" src="https://github.com/user-attachments/assets/913383e6-7c0f-444e-ae81-776d0e8b3f1a" />

### ii) Display the video
<img width="619" height="463" alt="Screenshot 2025-09-22 114915" src="https://github.com/user-attachments/assets/8760fb97-a0d8-4af1-a6db-8e80457bd7f7" />

### iii) Display the video by resizing the window
<img width="302" height="459" alt="Screenshot 2025-09-22 114923" src="https://github.com/user-attachments/assets/ac003c93-881b-4cc4-8930-8e3b240fb906" />

### iv) Rotate and display the video
<img width="345" height="460" alt="Screenshot 2025-09-22 114930" src="https://github.com/user-attachments/assets/0006a671-e015-4b5c-84e4-704afe863d16" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
