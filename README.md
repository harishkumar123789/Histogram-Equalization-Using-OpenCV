# Experiment 3 : Histogram Processing

### Developed By : HARISH KUMAR S
### Register Number : 212224230091

### Aim :
To study and implement histogram equalization for grayscale and color images using Python, OpenCV, NumPy, and Matplotlib to improve image contrast.

### Requirements :

* Jupyter Notebook / Anaconda Navigator
* Computer or laptop
* Sufficient storage space for Python libraries and image files
* Input image file: eagle.jpg

### Procedure
1. Import the required Python libraries: OpenCV (cv2), NumPy, and Matplotlib (pyplot).
2. Read the input image (eagle.jpg) in grayscale mode using OpenCV.
3. Display the original grayscale image using Matplotlib.
4. Calculate and plot the histogram of the original grayscale image using plt.hist().
5. Apply histogram equalization to the grayscale image using cv2.equalizeHist().
6. Display the equalized grayscale image and plot its histogram.
7. Read the input image again in color mode.
8. Convert the color image from BGR to HSV color space using cv2.cvtColor().
9. Apply histogram equalization to the Value (brightness) channel of the HSV image.
10. Convert the equalized HSV image back to BGR color space.
11. Display the original and equalized color images for comparison.
12. Plot the original and equalized image histograms to observe the changes in intensity distribution.

### Program : 

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('eagle.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

### Output : 

### Step1 : Histogram Equalization for Grayscale Images

<img width="411" height="527" alt="Screenshot 2026-11-17 234000" src="https://github.com/user-attachments/assets/9cc17329-268d-4ac1-83e3-183c99f8bf4d" />


<img width="707" height="522" alt="Screenshot 2026-11-17 234013" src="https://github.com/user-attachments/assets/961fda74-97d0-48c1-a6ff-f3029fdd9ab0" />


<img width="703" height="525" alt="Screenshot 2026-11-17 234029" src="https://github.com/user-attachments/assets/3ed70713-1334-41c5-923a-ca35d9889b66" />


<img width="417" height="522" alt="Screenshot 2026-11-17 234039" src="https://github.com/user-attachments/assets/824737e0-caa3-453a-b0bf-179143c7cc74" />





### Step2 : Histogram Equalization for Color Images

<img width="412" height="523" alt="Screenshot 2026-11-17 234050" src="https://github.com/user-attachments/assets/12b1ffbc-ebe9-4a48-ab60-9b1070a95b58" />


<img width="672" height="528" alt="Screenshot 2026-11-17 234102" src="https://github.com/user-attachments/assets/9b594b8b-7cb3-4000-b0b3-c1d24347d5f8" />


<img width="1455" height="503" alt="Screenshot 2026-11-17 234115" src="https://github.com/user-attachments/assets/5d2fd215-b223-4c18-a125-cdea074f10a4" />


<img width="1506" height="452" alt="Screenshot 2026-11-17 234127" src="https://github.com/user-attachments/assets/ee99fac6-bdd6-4eec-9e1c-388c019ce6b5" />


















### Result :

Thus , the Histogram equalization was successfully performed, improving the contrast of grayscale and color images.












            
