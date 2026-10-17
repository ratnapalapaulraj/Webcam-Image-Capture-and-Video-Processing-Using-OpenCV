# Image Capture and Video Processing Using OpenCV
### Developed By:
**Name:** RATNAPALA P
### Register No:
212225100037
---

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

## 💻 Program

```python
import cv2

# Initialize webcam
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    if not ret:
        print("Cannot access webcam")
        break

    # i) Save frame as JPG
    cv2.imwrite("captured_image.jpg", frame)

    # ii) Display the original video
    cv2.imshow("Original Video", frame)

    # iii) Display resized video
    resized = cv2.resize(frame, (640, 480))
    cv2.imshow("Resized Video", resized)

    # iv) Rotate and display video
    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    cv2.imshow("Rotated Video", rotated)

    # Press Q to stop
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Release webcam and close windows
cap.release()
cv2.destroyAllWindows()
```
---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
<img width="1076" height="515" alt="image" src="https://github.com/user-attachments/assets/9954d2a5-af55-43ee-ad94-9916d8e33b53" />


### ii) Display the video
Live webcam video is displayed original.
<img width="463" height="576" alt="image" src="https://github.com/user-attachments/assets/469e43a6-d44b-44ba-86ab-4fbfbc4d2fa8" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
<img width="587" height="528" alt="image" src="https://github.com/user-attachments/assets/2bd7b9a1-5b2f-408d-bc3c-951fd97f38ba" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
<img width="346" height="576" alt="image" src="https://github.com/user-attachments/assets/b5acda85-49c2-4597-a51a-299f1430a15a" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
