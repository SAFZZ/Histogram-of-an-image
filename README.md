# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step4:
cv2.equalize() is used to transform the gray image to equalized form.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program:

### Developed By: S.SAFA
### Register Number:212220230040


# a)Write your code to find the histogram of gray scale image and color image channels.
```
import cv2
import matplotlib.pyplot as plt 

#gray scale and color image  
gray_image = cv2.imread("moon.jpg")
color_image = cv2.imread("eyes.jpg")

#resizing and printing the image 
gray_image= cv2.resize(gray_image, (300,170))
cv2.imshow('GRAY IMAGE',gray_image)

color_image= cv2.resize(color_image, (300,170))
cv2.imshow('COLOR IMAGE',color_image)

cv2.waitKey(0)

```

# b)Display the histogram of gray scale image and any one channel histogram from color image
```
gray_hist=cv2.calcHist([gray],[0],None,[256],[0,255])
color_hist=cv2.calcHist([color],[2],None,[256],[0,255])
plt.figure()
plt.title("GRAY IMAGE")
plt.xlabel("GRAYSCALE VALUE")
plt.ylabel("PIXEL COUNT")
plt.stem(gray_hist)
plt.show()
plt.figure()
plt.title("COLOR IMAGE")
plt.xlabel("COLORSCALE VALUE")
plt.ylabel("PIXEL COUNT")
plt.stem(color_hist)
plt.show()
```
# c)Write the code to perform histogram equalization of the image. 
```
import cv2
Gray_image=cv2.imread('moon.jpg',0)
equalize=cv2.equalizeHist(Gray_image)
#resizing image 
Gray_image= cv2.resize(Gray_image, (270,190))
equalize= cv2.resize(equalize, (270,190))
#output
cv2.imshow('GRAY IMAGE',Gray_image)
cv2.imshow('EQUALIZED IMAGE',equalize)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
## Input Grayscale Image and Color Image
![exp 4 a](https://user-images.githubusercontent.com/75234912/165234234-45fb2825-bd64-401e-b4d7-b7b2c596d287.png)


## Histogram of Grayscale Image and any channel of Color Image

![exp 4b](https://user-images.githubusercontent.com/75234912/165234266-801e26ac-b706-440f-9f1a-aad3d6a4bf54.png)

## Histogram Equalization of Grayscale Image
![exp 4 c](https://user-images.githubusercontent.com/75234912/165234301-5141c647-9b2e-4963-ae6e-f3287da4bee7.png)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
