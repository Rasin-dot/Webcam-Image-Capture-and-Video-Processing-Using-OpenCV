# Image Capture and Video Processing Using OpenCV

### Name: Rasindhan R

### Register No: 212224230222

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

##  Program and Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Image Saved Successfully")

cap.release()
```

<img width="660" height="517" alt="image" src="https://github.com/user-attachments/assets/9ccc9221-2eb1-4a0b-94cd-d5c7c18aac4e" />


### ii) Display the video
Live webcam video is displayed
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()

```
<img width="647" height="485" alt="image" src="https://github.com/user-attachments/assets/1159ff06-5f5d-407d-a758-53448eda95be" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    # Resize the frame
    resized_frame = cv2.resize(frame, (640, 480))

    # Convert BGR to RGB
    resized_frame = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="328" height="482" alt="image" src="https://github.com/user-attachments/assets/17a7da60-ddc7-4b4c-83e7-aacb9ae9a604" />



### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    # Rotate the frame
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    # Convert BGR to RGB
    rotated_frame = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```


<img width="371" height="481" alt="image" src="https://github.com/user-attachments/assets/5d1ff093-2a6e-4083-b79a-5a4b8084228b" />



## Result

Thus, the image is successfully captured from thy captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
