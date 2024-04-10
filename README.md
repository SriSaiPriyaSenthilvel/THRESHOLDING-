# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
Developed by:Sri Sai Priya.S
Register Number:212222240103
```
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```
image = cv2.imread("thresholding.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("thresholding.jpg",0)
```
# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/7118b315-b568-4a35-87e9-96eef0f93e62)
<br>
<br>

### Global Thresholding

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/4a8533fb-8db5-42c2-aeff-7420c558d673)

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/455aff44-fe4f-4689-bddb-52df0d652b11)

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/883947c9-32ba-4b1a-ba11-b2ab08c3377b)

<br>
<br>

### Adaptive Thresholding

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/b873c827-2f51-46f8-a2d5-5192e7a69bcd)

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/6e38397d-5faf-4998-baa2-b515ecb962aa)

<br>
<br>

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/SriSaiPriyaSenthilvel/THRESHOLDING-/assets/119475702/5bfc44c3-fe5d-470c-85de-ef620fceb594)

<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
