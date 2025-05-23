# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries (NumPy, OpenCV, Matplotlib).

### Step2:
Read an image, convert it to RGB format, and display it using Matplotlib.Define translation parameters (e.g., shifting by 100 pixels horizontally and 200 pixels vertically).Perform translation using cv2.warpAffine().Display the translated image using Matplotlib.

### Step3:
Obtain the dimensions (rows, cols, dim) of the input image.Define a scaling matrix M with scaling factors of 1.5 in the x-direction and 1.8 in the y-direction.Perform perspective transformation using cv2.warpPerspective(), scaling the image by a factor of 1.5 in the x-direction and 1.8 in the y-direction.Display the scaled image using Matplotlib.

### Step4:
Define shear matrices M_x and M_y for shearing along the x-axis and y-axis, respectively.Perform perspective transformation using cv2.warpPerspective() with the shear matrices to shear the image along the x-axis and y-axis.Display the sheared images along the x-axis and y-axis using Matplotlib.

### Step5:
Define reflection matrices M_x and M_y for reflection along the x-axis and y-axis, respectively.Perform perspective transformation using cv2.warpPerspective() with the reflection matrices to reflect the image along the x-axis and y-axis.Display the reflected images along the x-axis and y-axis using Matplotlib.

### Step 6 :
Define an angle of rotation in radians (here, 10 degrees).Construct a rotation matrix M using the sine and cosine of the angle.Perform perspective transformation using cv2.warpPerspective() with the rotation matrix to rotate the image.Display the rotated image using Matplotlib.
### Step 7 :
Define a region of interest by specifying the desired range of rows and columns to crop the image (here, from row 100 to row 300 and from column 100 to column 300).Use array slicing to extract the cropped region from the input image.Display the cropped image using Matplotlib.


## Program:

#### Developed By: Sanjay Balaji S
#### Register Number: 212223240149
### i)Image Translation
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M = np.float32([[1, 0, 100],[0, 1, 200],[0, 0, 1]])

translated_image = cv2.warpPerspective(input_image, M, (cols, rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()
```
### ii) Image Scaling
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

rows, cols, dim = input_image.shape 
M = np.float32([[1.5, 0, 0],[0, 1.8, 0],[0, 0, 1]])

scaled_img=cv2.warpPerspective (input_image, M, (cols*2, rows*2))
plt.imshow(scaled_img)
plt.show()
```
### iii)Image shearing
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

M_x = np.float32([[1, 0.5, 0],[0, 1 ,0],[0,0,1]])
M_y =np.float32([[1, 0, 0],[0.5, 1, 0],[0, 0, 1]])

sheared_img_xaxis=cv2.warpPerspective(input_image,M_x, (int(cols*1.5), int(rows *1.5)))
sheared_img_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols*1.5), int(rows*1.5)))

plt.imshow(sheared_img_xaxis)
plt.show()

plt.imshow(sheared_img_yaxis)
plt.show()
```
### iv)Image Reflection
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

M_x= np.float32([[1,0, 0],[0, -1, rows],[0, 0, 1]])
M_y =np.float32([[-1, 0, cols],[ 0, 1, 0 ],[ 0, 0, 1 ]])
# Apply a perspective transformation to the image
reflected_img_xaxis=cv2.warpPerspective (input_image, M_x,(int(cols), int(rows)))
reflected_img_yaxis= cv2.warpPerspective (input_image, M_y, (int(cols), int(rows)))

                                         
plt.imshow(reflected_img_xaxis)
plt.show()

plt.imshow(reflected_img_yaxis)
plt.show()

```
### v)Image Rotation
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

angle=np.radians(10)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
rotated_img = cv2.warpPerspective(input_image,M,(int(cols),int(rows)))

plt.imshow(rotated_img)
plt.show()

```
### vi)Image Cropping
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("C:/Users/admin/SanjayBalaji/DIPT/Image.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

cropped_img= input_image[100:300,100:300]

plt.imshow(cropped_img)
plt.show()

```


## Output:
### i)Image Translation
![image](https://github.com/user-attachments/assets/78d7d376-b6b1-4b2c-8939-60e6e0b6337b)


### ii) Image Scaling
![image](https://github.com/user-attachments/assets/f81a4624-5556-42d0-b856-08dea48de8c8)


### iii)Image shearing
![image](https://github.com/user-attachments/assets/3f931c28-b59e-42a2-8d35-ab49d5439097)


### iv)Image Reflection
![image](https://github.com/user-attachments/assets/0be651da-68c8-46d1-bb9f-e5003a5f082f)


### v)Image Rotation
![image](https://github.com/user-attachments/assets/68fc9c0a-88c0-4064-89a4-77ce6635f1de)


### vi)Image Cropping
![image](https://github.com/user-attachments/assets/befc8789-fa70-4be4-9a48-45c1be01d5c9)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
