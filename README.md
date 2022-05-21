# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

</br>
</br>
</br>

## PROGRAM:
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("army.webp",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("army.webp",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
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

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## OUTPUT:

### Original Image and Grayscale Image
![o1](https://user-images.githubusercontent.com/77089743/169637663-dd73785c-20ab-46d9-a5f3-7c37f66e7237.PNG)



### Global Thresholding
![o2](https://user-images.githubusercontent.com/77089743/169637687-e3e12061-52ee-4d0b-b9c6-bb019309f26d.PNG)

![o3](https://user-images.githubusercontent.com/77089743/169637690-8207b685-e990-4fc0-8ee2-dddcf30bf3fd.PNG)

![o4](https://user-images.githubusercontent.com/77089743/169637703-20894f58-6d7f-44f4-b974-f3774ab612b7.PNG)

![o5](https://user-images.githubusercontent.com/77089743/169637704-1c58a132-95a6-4ad1-ae3f-18d3632331a7.PNG)

![o6](https://user-images.githubusercontent.com/77089743/169637701-40b75751-1e1b-4d1e-92e9-6a639be2fb22.PNG)




### Adaptive Thresholding


![o8](https://user-images.githubusercontent.com/77089743/169637729-70c7029d-3fa6-4f93-ba5f-aa13f8752218.PNG)

![o7](https://user-images.githubusercontent.com/77089743/169637732-aa01294e-d036-4535-845d-20995ac919bb.PNG)


### Optimum Global Thesholding using Otsu's Method


![o9](https://user-images.githubusercontent.com/77089743/169637767-cd0b64f0-5085-4678-a8e0-3f61b1e791e3.PNG)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
