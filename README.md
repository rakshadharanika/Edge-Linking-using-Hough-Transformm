# Edge-Linking-using-Hough-Transformm
### NAME   : V RAKSHA DHARANIKA
### REG NO : 212223230167
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
image = cv2.imread('fish.jpg') 
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/4c62d880-1d1b-4884-8201-57c2c1d3ad45)

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/fa4f7b77-21ff-4c2e-bfb5-2710896e969b)


### Canny Edge detector output
```

canny = cv2.Canny(gray_blur, 120, 150)
plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/2938845b-70bc-445a-b916-acd23c781071)



### Display the result of Hough transform
```

lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)

# DISPLAY THE FINAL RESULT
plt.imshow(img_c)
plt.title("Result Image with Lines")
plt.axis("off")
plt.show()



```
![image](https://github.com/user-attachments/assets/6475f41a-0a20-42d2-8048-4c26e1e16bcc)


### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
