# Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour
Digital Image Processing Object detection using Morphological Operations and Contour
##
# Problem 1
#### calculate the centroids of each object and display them in red color. Note: you cannot use Image Moments to find centroids
## input image 
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/data/circle3.jpg)
##
#### 1: Define the structuring element for dilation and erosion as a 3x3 matrix filled with ones using NumPy's np.ones() function.
#### 2: Apply erosion operation on the input image img using the cv2.erode() function with the defined kernel and 5 iterations, and store the result in the img_erosion variable.
#### 3: Apply dilation operation on the eroded image img_erosion using the cv2.dilate() function with the same kernel and iterations, and store the result in the img_dilation variable.
#### 4: Threshold the dilated image img_dilation using the cv2.threshold() function to convert it to a binary image.
#### 5: Find contours in the thresholded image using the cv2.findContours() function, and store the contours and hierarchy in the contours and hierarchy variables, respectively.
#### 6: Loop over each contour in contours, calculate its centroid using the cv2.boundingRect() function, and append it to the centroids list.
## output
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.35.11%20PM.png)
##
# Fill the holes of these objects (figure-1 a) using Morphological Dilation as discussed in class. You can use the centroids calculated in a) as marker points for dilation to fill the centers.
##
###### 1- Define a 15x15 cross-shaped kernel for dilation
###### 2- Create a marker image with the centroids in white color. The marker image is initialized with all zeros using np.zeros_like() function and then the centroids are set to 255 (white).
###### 3- Apply dilation to the marker image with the kernel defined in step 2 to fill the centers using cv2.dilate() function and store the result in dilated_img
## output
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.35.51%20PM.png)
