# EXPERIMENT 02: Record-Image Acquisition Using Web Camera

**Name:** PRAHATHIESWARAN S 

**Register Number:** 212225240107

---

## Aim

To acquire an image from a web camera, save the captured frame as a JPG file, display video frames, resize the video frames, and rotate and display the video using OpenCV and Matplotlib in Python.

---

## Software Required

- Python 3.x
- OpenCV (`opencv-python`)
- Matplotlib (`matplotlib`)
- IPython / Jupyter Notebook
- A working web camera

---

## Algorithm

### 1. Image Acquisition and Saving the Frame

1. Import the required libraries: `cv2`, `matplotlib.pyplot`, `clear_output`, and `time`.
2. Open the web camera using `cv2.VideoCapture(0)`.
3. Read a frame from the camera using `cap.read()`.
4. If a frame is successfully captured, save it as `captured_frame.jpg` using `cv2.imwrite()`.
5. Release the camera using `cap.release()`.
6. Read the saved JPG image using `cv2.imread()`.
7. Convert the image from BGR to RGB for correct display with Matplotlib, and display it with the title **Captured Frame**.

### 2. Displaying the Video

1. Open the web camera using `cv2.VideoCapture(0)`.
2. Read up to 50 frames from the camera.
3. Stop the loop if a frame cannot be captured.
4. Convert each frame from BGR to RGB using `cv2.cvtColor()`.
5. Clear the previous output and display the current frame using Matplotlib.
6. Add a short delay between frames and release the camera after the loop.

### 3. Displaying the Resized Video

1. Open the web camera and capture up to 50 frames.
2. Resize each frame to **100 × 150 pixels** using `cv2.resize()`.
3. Convert the resized frame from BGR to RGB.
4. Clear the previous output and display the resized frame.
5. Add a short delay and release the camera after the loop.

### 4. Rotating and Displaying the Video

1. Open the web camera and capture up to 50 frames.
2. Rotate each frame by 90 degrees clockwise using `cv2.rotate()` and `cv2.ROTATE_90_CLOCKWISE`.
3. Convert the rotated frame from BGR to RGB.
4. Clear the previous output and display the rotated frame.
5. Add a short delay and release the camera after the loop.

---

## Program

### 1. Record an Image and Save It as a JPG File

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

# Capture a frame from the web camera
cap = cv2.VideoCapture(0)
ret, frame = cap.read()

# Save the captured frame as a JPG file
if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

# Read and display the saved image
captured_image = cv2.imread("captured_frame.jpg")

if captured_image is not None:
    plt.imshow(captured_image[:, :, ::-1])
    plt.title("Captured Frame")
    plt.axis("off")
    plt.show()
else:
    print("Unable to load the captured image.")
```

<<<<<<< HEAD
**Output image:** Upload your captured image here, for example `captured_frame.jpg`.

![Captured Frame](captured_frame.jpg)
=======
<img width="512" height="410" alt="image" src="https://github.com/user-attachments/assets/eb45b1ab-ea25-42ca-8bfa-14f5082c0919" />

>>>>>>> a025634b3a62b1aa10a3b8674b1ea8f12d11c9be

### 2. Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()
    time.sleep(0.05)

cap.release()
```

<<<<<<< HEAD
**Output image:** Upload a screenshot of the displayed video here.

![Video Display](video_display.png)
=======

<img width="512" height="389" alt="image" src="https://github.com/user-attachments/assets/b0a7009b-bf6e-4493-bf2f-84d0ff3d53e0" />
>>>>>>> a025634b3a62b1aa10a3b8674b1ea8f12d11c9be

### 3. Display the Video by Resizing the Frame

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()
    time.sleep(0.05)

cap.release()
```

<<<<<<< HEAD
**Output image:** Upload a screenshot of the resized video here.

![Resized Video](resized_video.png)
=======
<img width="266" height="389" alt="image" src="https://github.com/user-attachments/assets/b018fe70-c3ac-4ee7-a544-c86696097550" />
>>>>>>> a025634b3a62b1aa10a3b8674b1ea8f12d11c9be

### 4. Rotate and Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()
    time.sleep(0.05)

cap.release()
```
<<<<<<< HEAD

**Output image:** Upload a screenshot of the rotated video here.

![Rotated Video](rotated_video.png)
=======
<img width="297" height="389" alt="image" src="https://github.com/user-attachments/assets/e2c4721c-7b8c-4043-87cb-2b6e45446f73" />
>>>>>>> a025634b3a62b1aa10a3b8674b1ea8f12d11c9be

---

## Result

Thus, image acquisition using a web camera was performed successfully using Python, OpenCV, and Matplotlib. The captured frame was saved as a JPG file, and video frames were displayed, resized, and rotated.
