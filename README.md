# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- **Name:**  Venkata Mohan N
- **Register No:**   212224230298
```

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('mk.png')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')


sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions


plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')


canny_edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  

```
---

## Output

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions

- <img width="370" height="522" alt="image" src="https://github.com/user-attachments/assets/d950664b-8fbf-452b-93ab-7ad7960960b8" />
 
- Produces gradient-based edge map

- <img width="384" height="505" alt="image" src="https://github.com/user-attachments/assets/be50bde5-4232-400e-8998-7c7850147ad3" />


###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel

- <img width="379" height="508" alt="image" src="https://github.com/user-attachments/assets/79b25020-539a-4db3-9936-69e32e11c02a" />

- Detects directional edges  

###  Roberts Edge Detector
- Detects edges using diagonal gradients

- <img width="462" height="492" alt="image" src="https://github.com/user-attachments/assets/0bbe9e5d-ebb0-48b4-984e-df1dd604bc48" />

- Sensitive to noise  

###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes

<img width="373" height="487" alt="image" src="https://github.com/user-attachments/assets/b6ca62ba-a2b1-486f-bf19-b0d18bd2e695" />


###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges

- <img width="439" height="538" alt="image" src="https://github.com/user-attachments/assets/8a0c74d5-2ebd-44a6-afbf-d4c568b623a3" />


---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
