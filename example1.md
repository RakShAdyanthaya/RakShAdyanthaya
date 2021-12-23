```python
pip install opencv-python
```

    Requirement already satisfied: opencv-python in c:\users\pc16\anaconda3\lib\site-packages (4.5.4.60)
    Requirement already satisfied: numpy>=1.19.3 in c:\users\pc16\anaconda3\lib\site-packages (from opencv-python) (1.20.3)
    Note: you may need to restart the kernel to use updated packages.
    


```python
import cv2
```


```python
img=cv2.imread("scean.jpg")
```


```python
#displaying image
```


```python
cv2.imshow('image window',img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


```python
#changing color
```


```python
# importing cv2
import cv2
from matplotlib import pyplot as plt
# path
path =  r'E:\Raksha Adyanthaya\dowloadedpics\scean.jpg'


# Reading an image in default mode
image = cv2.imread(path)

# Window name in which image is displayed
window_name = 'Image'

# Using cv2.imshow() method
# Displaying the image
image=cv2.cvtColor(image,cv2.COLOR_BGR2HSV)
#cv2.imshow(window_name, image)
plt.imshow(image)
#waits for user to press any key
#(this is necessary to avoid Python kernel form crashing)
cv2.waitKey()

#closing all open windows
cv2.destroyAllWindows()
```


```python
#displaying 4 images
```


```python
import cv2
from matplotlib import pyplot as plt
  
# create figure
fig = plt.figure(figsize=(10, 7))
  
# setting values to rows and column variables
rows = 2
columns = 2
  
# reading images
Image1 = cv2.imread('baby1.jpg')
Image2 = cv2.imread('baby2.jpg')
Image3 = cv2.imread('scean.jpg')
Image4 = cv2.imread('scean.jpg')
  
# Adds a subplot at the 1st position
fig.add_subplot(rows, columns, 1)
  
# showing image
plt.imshow(Image1)
plt.axis('off')
plt.title("First")
  
# Adds a subplot at the 2nd position
fig.add_subplot(rows, columns, 2)
  
# showing image
plt.imshow(Image2)
plt.axis('off')
plt.title("Second")
  
# Adds a subplot at the 3rd position
fig.add_subplot(rows, columns, 3)
  
# showing image
plt.imshow(Image3)
plt.axis('off')
plt.title("Third")
  
# Adds a subplot at the 4th position
fig.add_subplot(rows, columns, 4)
  
# showing image
plt.imshow(Image4)
plt.axis('off')
plt.title("Fourth")
```


```python
#scaling-resizing 
```


```python
import cv2
from matplotlib import pyplot as plt

img=cv2.imread('baby2.jpg',cv2.IMREAD_COLOR)

resized=cv2.resize(img,None,fx=1,fy=2,interpolation=cv2.INTER_CUBIC)
plt.imshow(img)


plt.imshow(resized)

cv2.waitKey(0)
cv2.destroyAllWindows()

```


```python
#translation-shifting object
```


```python
import numpy as np
import cv2
from matplotlib import pyplot as plt
img = cv.imread('baby1.jpg',0)
rows,cols = img.shape
M = np.float32([[1,0,100],[0,1,50]])
dst = cv.warpAffine(img,M,(cols,rows))
plt.imshow(dst)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


```python
#rotation
```


```python
img = cv.imread('baby4.jpg',0)
rows,cols = img.shape
# cols-1 and rows-1 are the coordinate limits.
M = cv.getRotationMatrix2D(((cols-1)/2.0,(rows-1)/2.0),90,1)
dst = cv.warpAffine(img,M,(cols,rows))
plt.imshow(dst)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


```python
#Affine Transformation
```


```python

import numpy as np
import cv2 as cv
img = cv.imread('baby2.jpg')
rows,cols,ch = img.shape
pts1 = np.float32([[50,50],[200,50],[50,200]])
pts2 = np.float32([[10,100],[200,50],[100,250]])
M = cv.getAffineTransform(pts1,pts2)
dst = cv.warpAffine(img,M,(cols,rows))
plt.subplot(121),plt.imshow(img),plt.title('Input')
plt.subplot(122),plt.imshow(dst),plt.title('Output')
cv2.imshow('image window',img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


```python
#Perspective Transformation
```


```python
img = cv.imread('baby3.jpg')
rows,cols,ch = img.shape
pts1 = np.float32([[56,65],[368,52],[28,387],[389,390]])
pts2 = np.float32([[0,0],[300,0],[0,300],[300,300]])
M = cv.getPerspectiveTransform(pts1,pts2)
dst = cv.warpPerspective(img,M,(300,300))
plt.subplot(121),plt.imshow(img),plt.title('Input')
plt.subplot(122),plt.imshow(dst),plt.title('Output')
plt.show()
```


```python
#for loop
```


```python
text = "Python"

for character in text:
    print(character)
    
```

    P
    y
    t
    h
    o
    n
    


```python
list=[10,20,30,40,50,60]
n=6
for i in list:
    if i%2==0:
        c=n*i
        print(c)
print("MULTIPLE OF 10")
```

    60
    120
    180
    240
    300
    360
    MULTIPLE OF 10
    


```python
print("Enter Marks Obtained in 5 Subjects: ")
markOne = int(input())
markTwo = int(input())
markThree = int(input())
markFour = int(input())
markFive = int(input())

tot = markOne+markTwo+markThree+markFour+markFive
avg = tot/5

if avg>=80 and avg<=90:
    print("Distinction")
elif avg>=91 and avg<100:
    print("Rank Holder")
elif avg>=60 and avg<80:
    print("FIRST class")
elif avg>=50 and avg<60:
    print("second class")
elif avg>=35 and avg<50:
    print("Pass")
elif avg>=0 and avg<35 :
    print("FAIL")

else:
    print("Invalid Input!")
```

    Enter Marks Obtained in 5 Subjects: 
    54
    47
    25
    15
    64
    Pass
    


```python
weeks=['Monday','Tuesday','Wednesday','Thursday','Friday','Saturday','Sunday']

for x in weeks:
    if x=='Sunday':
     print('No Harish sir class in Sunday')
     continue
    if x=='Monday':
     print('No Harish sir class in Monday')   
     continue
    if x=='Tuesday':
     print('No Harish sir class in Tuesday')   
     continue
    if x=='Saturday':
     print('No Harish sir class in Saturday')   
     continue
    print(x)
```

    No Harish sir class in Monday
    No Harish sir class in Tuesday
    Wednesday
    Thursday
    Friday
    No Harish sir class in Saturday
    No Harish sir class in Sunday
    


```python

```
