# Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour
Digital Image Processing Object detection using Morphological Operations and Contour
##
# Problem 1
#### calculate the centroids of each object and display them in red color. Note: you cannot use Image Moments to find centroids
## input image 
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/data/circle3.jpg)
#### solution
1: Define the structuring element for dilation and erosion as a 3x3 matrix filled with ones using NumPy's np.ones() function.
2: Apply erosion operation on the input image img using the cv2.erode() function with the defined kernel and 5 iterations, and store the result in the img_erosion variable.
3: Apply dilation operation on the eroded image img_erosion using the cv2.dilate() function with the same kernel and iterations, and store the result in the img_dilation variable.
4: Threshold the dilated image img_dilation using the cv2.threshold() function to convert it to a binary image.
5: Find contours in the thresholded image using the cv2.findContours() function, and store the contours and hierarchy in the contours and hierarchy variables, respectively.
6: Loop over each contour in contours, calculate its centroid using the cv2.boundingRect() function, and append it to the centroids list.
## Result
![input](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.35.11%20PM.png)
