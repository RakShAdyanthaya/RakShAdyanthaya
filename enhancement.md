```python
from PIL import Image
from PIL import ImageEnhance
 
# Opens the image file
image = Image.open('baby2.jpg')  
 
# shows image in image viewer
image.show()  
 
 
# Enhance Brightness
curr_bri = ImageEnhance.Brightness(image)
new_bri =5
 
# Brightness enhanced by a factor of 2.5
img_brightened = curr_bri.enhance(new_bri)
 
# shows updated image in image viewer
img_brightened.show()  
```


```python
from PIL import Image
from PIL import ImageEnhance
 
# Opens the image file
image = Image.open('baby3.jpg')
 
# shows image in image viewer
image.show()
 
 
# Enhance Contrast
curr_con = ImageEnhance.Contrast(image)
new_con = 0.3
 
# Contrast enhanced by a factor of 0.3
img_contrasted = curr_con.enhance(new_con)
 
# shows updated image in image viewer
img_contrasted.show()  

```


```python

```
