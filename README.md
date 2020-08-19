# Sort-Contour-By-Distance

Many times we want to sort the contours is similar manner we write. For that built-in function for CV2 does not help that much.
For sorting it in a correct manner we calculate distance between each contours to find minimum distance. Here the distance is define as the midpoint of the a contour of the right-side to midpoint of the left side of another contour. Sort all contours by minimum distance. If we get minimum distance between contour and the right-edge of the image, that mean we now need to change the line. 

## Example Image
Taking a test image and after Image Pre-Processing, image will look this:
```python
image = cv2.imread("Final.jpg")
```
![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Final.jpg)

## Creating Contours
Creating contours it will look like this:
```python
cnts = cv2.findContours(dilate.copy(), cv2.RETR_EXTERNAL,cv2.CHAIN_APPROX_SIMPLE)
```

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/box.jpg)

## Using Built-in Function
After using 'sorted' functon of CV2:
```python
sorted_ctrs = sorted(cnts, key=lambda ctr: cv2.boundingRect(ctr)[0] + cv2.boundingRect(ctr)[1] * image.shape[1])
```

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Screenshots/Sort-by-bultin-func.PNG)

## Sort by Distances
Sorting by distance between contours:

![alt text](https://github.com/Harsh120/Sort-Contour-By-Distance/blob/master/Screenshots/Sort-by-distance.PNG)
