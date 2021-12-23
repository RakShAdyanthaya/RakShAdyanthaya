```python
import cv2
# import Numpy
import numpy as np
from matplotlib import pyplot as plt
# reading an image using imreadmethod
my_img = cv2.imread('baby1.jpg', 0)
equ = cv2.equalizeHist(my_img)
# stacking both the images side-by-side orientation
res = np.hstack((my_img, equ))
# showing image input vs output
cv2.imshow('image', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


```python
hist,bins = np.histogram(equ.flatten(),256,[0,256])
cdf = hist.cumsum()
cdf_normalized = cdf * float(hist.max()) / cdf.max()
plt.plot(cdf_normalized, color = 'b')
plt.hist(equ.flatten(),256,[0,256], color = 'r')
plt.xlim([0,256])
plt.legend(('cdf','histogram'), loc = 'upper left')
plt.show()

```


```python

```
