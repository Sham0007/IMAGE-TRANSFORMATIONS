
## Ex.No:04
## IMAGE TRANSFORMATION
## NAME : SARAVANAN SHAM PRAKASH
## REG NO : 212224230254


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:

Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:

Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:

## i) Original Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```
image=cv2.imread("Chennai.png")
image.shape
```

```
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```

## ii)Image Translation
```
# i) Image Translation
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
```

```
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```

## iii) Image Scaling
```
# Image Scaling
fx,fy=2.0,1.0
scaled_image=cv2.resize(image,None,fx=fx,fy=fy, interpolation=cv2.INTER_LINEAR)
```

## iv)Image shearing
```
# Image Shearing
shear_matrix=np.float32([[1,0.5,0],[0.5,1,0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (673, 419))
```

```
plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image")
plt.axis('on')
plt.show()
```

## v)Image Reflection
```
# Image Reflection
reflected_image = cv2.flip(image, 2)
```

```
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## vi)Image Rotation
```
# Image Rotation
(height,width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation=cv2.getRotationMatrix2D(center,angle,1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
```

```
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis("off")
```

## vii)Image Cropping
```
angle = 145
center = (673 // 2, 419 // 2)
M_rotation=cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
```

```
plt.imshow(rotated_image[:,:,::-1])
plt.title("Rotated Image")
plt.axis("off")
plt.show()
```

## Output:
### i) Original Image

<img width="787" height="481" alt="Screenshot 2025-09-03 142045" src="https://github.com/user-attachments/assets/969efa84-1933-4f0d-9c06-5cc2bb752228" />

### ii)Image Translation

<img width="701" height="476" alt="Screenshot 2025-09-03 142058" src="https://github.com/user-attachments/assets/f45016d5-5834-42aa-8560-c817db3d6db7" />

### iii) Image Scaling

<img width="886" height="345" alt="Screenshot 2025-09-03 142113" src="https://github.com/user-attachments/assets/6d9f0abb-c36d-4323-97f7-679b7c1a167e" />

### iv)Image shearing

<img width="746" height="464" alt="Screenshot 2025-09-03 142145" src="https://github.com/user-attachments/assets/91a502b3-a2cf-40d4-9735-12f0c58e3528" />

### v)Image Reflection

<img width="912" height="323" alt="Screenshot 2025-09-03 142158" src="https://github.com/user-attachments/assets/51e8ee40-d97a-4d5e-ac79-9933d3894504" />

### vi)Image Rotation

<img width="735" height="444" alt="Screenshot 2025-09-03 142222" src="https://github.com/user-attachments/assets/124b7e43-d7e0-4f49-a70d-a3332865a6f0" />

### vi)Image Cropping

<img width="891" height="376" alt="Screenshot 2025-09-03 142233" src="https://github.com/user-attachments/assets/73090d53-04bb-467c-afe1-90b2cf2e4f85" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
