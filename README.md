# EX NO – 10  
# IMPLEMENT OPENING AND CLOSING USING PYTHON AND OPENCV

---

# Aim

To implement Morphological Opening and Closing operations using Python and OpenCV on a text image and visualize the output using Matplotlib.

---

# Software Required

- Anaconda – Python 3.7  
- OpenCV  
- NumPy  
- Matplotlib  

---

# Algorithm

## Opening Operation

### Step 1:
Import required libraries such as OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a blank black image using NumPy.

### Step 3:
Add text to the image using `cv2.putText()`.

### Step 4:
Create a structuring element (kernel) of size 3 × 3.

### Step 5:
Apply Morphological Opening using `cv2.morphologyEx()` with `cv2.MORPH_OPEN`.

### Step 6:
Convert the images from BGR to RGB format for display.

### Step 7:
Display the original and opened images using Matplotlib.

---

## Closing Operation

### Step 1:
Use the same input image and kernel.

### Step 2:
Apply Morphological Closing using `cv2.morphologyEx()` with `cv2.MORPH_CLOSE`.

### Step 3:
Convert the output image from BGR to RGB format.

### Step 4:
Display the original and closed images using Matplotlib.

---

# Program

### Developed By : Kiruba RC  
### Register Number : 212224230125

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX

cv2.putText(image,
            'Kiruba',
            (100, 250),
            font,
            1,
            (255, 255, 255),
            2,
            cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display input image
plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis('off')

# Opening operation
opened_image = cv2.morphologyEx(image,
                                cv2.MORPH_OPEN,
                                kernel)

# Display opening result
plt.subplot(1,3,2)
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))
plt.title("Opening Operation")
plt.axis('off')

# Closing operation
closed_image = cv2.morphologyEx(image,
                                cv2.MORPH_CLOSE,
                                kernel)

# Display closing result
plt.subplot(1,3,3)
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))
plt.title("Closing Operation")
plt.axis('off')

plt.show()
```

---

# Output

## Input Image with Text

<img width="514" height="556" alt="image" src="https://github.com/user-attachments/assets/11994a37-80dd-4787-a408-69301a7b74f2" />


## Opening Operation

<img width="543" height="561" alt="image" src="https://github.com/user-attachments/assets/d85e0b18-0048-4810-9eca-e075972e2e36" />


## Closing Operation

<img width="553" height="563" alt="image" src="https://github.com/user-attachments/assets/5762ef4c-59a8-4b80-af92-2338fb23fcb4" />


---


# Result

Thus the Morphological Opening and Closing operations are successfully implemented using Python and OpenCV. The original, opened, and closed images are displayed successfully using Matplotlib.
