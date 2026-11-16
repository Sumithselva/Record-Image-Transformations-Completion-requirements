
# Record-Image Transformations


---
## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
**Name:** SUMITH M

### Register No:
212224230279

---

##  Output

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('istockphoto-472018064-612x612.jpg') 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off') 
```
<img width="763" height="422" alt="image" src="https://github.com/user-attachments/assets/5c907d5a-d5ef-4d2b-8fbb-670772f28a85" />



```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  

translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')
```
<img width="752" height="438" alt="image" src="https://github.com/user-attachments/assets/32d28b30-bb67-49e5-84f7-400fe9f2fac2" />


```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```
<img width="726" height="201" alt="image" src="https://github.com/user-attachments/assets/c2c46465-a6f9-45bc-80aa-c0d759879188" />


```
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  # Set title
plt.axis('off')
```
<img width="705" height="426" alt="image" src="https://github.com/user-attachments/assets/a8d6dfa5-4fd3-4a80-ab9a-42b368edf795" />


```
# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```
<img width="737" height="427" alt="image" src="https://github.com/user-attachments/assets/e0fe0c72-e582-4200-a93a-c36120e73186" />


```
# Step 6: Image Rotation
(height, width) = image.shape[:2]  
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')
```
<img width="762" height="422" alt="image" src="https://github.com/user-attachments/assets/cd8b6712-6e3a-46ba-b801-8dd3d767826f" />

```
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
<img width="751" height="575" alt="image" src="https://github.com/user-attachments/assets/b6214632-c27b-4ead-9cb2-4a07ef182b3b" />


##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.


