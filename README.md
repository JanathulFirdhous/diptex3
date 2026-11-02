# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---
### Developed By:
**Name:** Janathul Firdhous A

### Register No: 212224040129
____________________________  

## Program
## 1. Import the required libraries and read the grayscale image.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('janna.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
## 2. Plot the histogram of the grayscale image.
```
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```
## 3. Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
```
## 4. Display the histogram of the equalized image.
```
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
## 5. Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
## 6. Read the image in color mode and convert to HSV.
```
img = cv2.imread('janna.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
## 7. Apply histogram equalization to the V channel.
```
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
## 8. Convert the enhanced HSV image back to BGR.
```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
## 9. Display the original and equalized color images.
```
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```
## 10. Display the original and equalized images along with their histograms.
```
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

---


---

##  Output
<img width="308" height="341" alt="image" src="https://github.com/user-attachments/assets/c0378730-cccd-492f-841b-dcfdba56eadb" />







<img width="467" height="341" alt="image" src="https://github.com/user-attachments/assets/6d23fa00-edbf-46f9-9077-77eb2e3ecda3" />








<img width="491" height="342" alt="image" src="https://github.com/user-attachments/assets/843f9271-c3cf-45d5-94d5-abbcf4b7aec3" />



<img width="322" height="347" alt="image" src="https://github.com/user-attachments/assets/bf72382a-7275-40ee-9b0a-b93b9506ae98" />







<img width="301" height="338" alt="image" src="https://github.com/user-attachments/assets/1c2c32d9-27b9-4ded-8414-a670050f7868" />







<img width="509" height="332" alt="image" src="https://github.com/user-attachments/assets/53cf3e9c-8939-4f74-b494-f6d8b38374f8" />








<img width="842" height="306" alt="image" src="https://github.com/user-attachments/assets/3979aa3a-7fa6-4eac-b04b-c53238b1378d" />







<img width="835" height="256" alt="image" src="https://github.com/user-attachments/assets/e373287a-54ff-444b-b869-eab02464b935" />

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
