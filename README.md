# Sort-Contour-By-Distance

Many times we want to sort the contours as the same as the sequence we write. For that built-in function for CV2 does not help that much.
For sorting it in a correct manner we calculate distance of each contours.

## Example Image
These is my test image:
'''python
image = cv2.imread("Final.jpg")
'''
![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Final.jpg)

## Creating Contours
'''
cnts = cv2.findContours(dilate.copy(), cv2.RETR_EXTERNAL,cv2.CHAIN_APPROX_SIMPLE)
'''

Creating contours it will look like this:

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/box.jpg)

## Using Built-in Function
'''
sorted_ctrs = sorted(cnts, key=lambda ctr: cv2.boundingRect(ctr)[0] + cv2.boundingRect(ctr)[1] * image.shape[1])
'''
After using 'sorted' functon of CV2 I got this:

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Screenshots/Sort-by-bultin-func.PNG)

## Sort by Distances
But that's not what we want, that's why I make my own alogrithm to sort it by distance

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Screenshots/Sort-by-distance.PNG)
