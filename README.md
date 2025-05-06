# Exp No 7: Edge-Linking-using-Hough-Transform

### Name: V Raksha dharanika
### Register No: 2122232301167


## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program 

### Input image and grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('spyd.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/97a8a253-17b8-4cf7-9c3e-679bb8e7ab2b)

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/1158b86b-5c7b-4ce9-a7c4-1a55f38f1629)


### Canny Edge detector output
```

canny = cv2.Canny(gray_blur, 120, 150)


plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/e99f7a5a-4c6a-44b6-8296-b19c86f27e8d)


### Display the result of Hough transform
```
lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)


if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)


plt.imshow(img_c)
plt.title("Result Image with Lines")
plt.axis("off")
plt.show()



```
![image](https://github.com/user-attachments/assets/fdd8fad0-87d2-4b35-96a7-daa755448d42)

### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
