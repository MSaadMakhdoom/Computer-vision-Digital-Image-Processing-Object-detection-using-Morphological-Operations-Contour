# Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour
Digital Image Processing Object detection using Morphological Operations and Contour
##
#### calculate the centroids of each object and display them in red color. Note: you cannot use Image Moments to find centroids
## input image 
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/data/circle3.jpg)
##
* Define the structuring element for dilation and erosion as a 3x3 matrix filled with ones using NumPy's np.ones() function.
* Apply erosion operation on the input image img using the cv2.erode() function with the defined kernel and 5 iterations, and store the result in the img_erosion variable.
* Apply dilation operation on the eroded image img_erosion using the cv2.dilate() function with the same kernel and iterations, and store the result in the img_dilation variable.
* Threshold the dilated image img_dilation using the cv2.threshold() function to convert it to a binary image.
* Find contours in the thresholded image using the cv2.findContours() function, and store the contours and hierarchy in the contours and hierarchy variables, respectively.
* Loop over each contour in contours, calculate its centroid using the cv2.boundingRect() function, and append it to the centroids list.
## output
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.35.11%20PM.png)
##
# Fill the holes of these objects (figure-1 a) using Morphological Dilation as discussed in class. You can use the centroids calculated in a) as marker points for dilation to fill the centers.
##
* Define a 15x15 cross-shaped kernel for dilation
* Create a marker image with the centroids in white color. The marker image is initialized with all zeros using np.zeros_like() function and then the centroids are set to 255 (white).
* Apply dilation to the marker image with the kernel defined in step 2 to fill the centers using cv2.dilate() function and store the result in dilated_img
## output
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.35.51%20PM.png)

##
# Calculate the diameter of the biggest hole (figure-1 a) and display its diameter above that circle in green color.
##

* Threshold the input image to create a binary image where white represents the region of interest.
* Find contours in the binary image using cv2.findContours() function.
* Create a copy of the input image to draw the diameter of the largest circle on.
* Keep track of the contour with the largest diameter found so far.
* Draw a circle with the diameter on the copy of the input image and display the diameter value on the image.
* Draw a rectangle with the largest diameter on the copy of the input image.

![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.36.02%20PM.png)
#

# count the number of objects with holes and without holes and display the count
##
* Thresholding method is applied to create a binary image, where the background is black and the objects are white.
* The findContours() function from OpenCV is used to find contours in the binary image.
* Two counters are initialized to keep track of the number of circles with and without holes.
* The code loops over each contour found in the image.
* For each contour, the area is calculated using the contourArea() function.
* The code checks if the area of the contour is within a certain range to filter out noise.
# output
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.36.15%20PM.png)

#
#
#
## For the image shown in Figure 2, find the number of persons in the image. Draw a bounding box around each person and display the image.
* Apply bilateral filtering on the input image img with a filter size of 15x15 and sigma values of 15.
* Threshold the filtered image using a threshold value of 140, and set all pixel values below this threshold to 0. The thresholding mode used here is cv2.THRESH_TOZERO, which means all pixel values above the threshold are kept as is, while pixel values below the threshold are set to 0.
* Define a 5x5 kernel of ones to use for morphological operations.
* Perform erosion operation on the thresholded image to remove small objects and noise.
* Perform dilation operation on the eroded image to fill in gaps and expand the remaining objects.
* Find contours in the dilated image using cv2.findContours function. The cv2.RETR_EXTERNAL flag retrieves only the external contours and cv2.CHAIN_APPROX_SIMPLE compresses horizontal, vertical, and diagonal segments and leaves only their end points.
* Define minimum and maximum area thresholds for the detected contours.
* Draw a green bounding box around each remaining contour in the img_bbox image.
#### preprocessing 
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.36.29%20PM.png)
#
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.36.42%20PM.png)
