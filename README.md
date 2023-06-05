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
#
#
#
#  For the image shown in Figure 1, count the number of text lines in the image
* Apply adaptive thresholding to create a binary image with the text in black and background in white
* Apply morphological operations dilation fill gaps in the text
* connected component analysis on the binary image dilation, which means that it identifies distinct regions of the image that are connected together.
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.36.53%20PM.png)
#
#
#
# Count the number of words in the given image
* Apply adaptive thresholding to create a binary image with the text in black and background in white
* Apply morphological operations dilation fill gaps in the word
* connected component analysis on the binary image dilation, which means that it identifies distinct regions of the image that are connected together.
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.37.07%20PM.png)
#
#
#
# Consider the Sudoku game image shown in Figure 4. Only identify the empty squares, color them red,and display the output image. The rest of the squares will remain unchanged.
* Convert the image to grayscale and apply adaptive thresholding
* Apply morphological operations to remove noise and fill gaps
* Apply connected component analysis to identify the empty squares
* Compare the original image with the processed image and replace the pixel values accordingly
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.37.16%20PM.png)
#
#
#
# shows an image of the Urdu alphabet. All these characters have different widths and heights. For instance, Alif is thin but tall. Similarly, Pay has a more extended width than height and three associated dots.
#
# Write a program that displays all characters whose width exceeds their height.
#
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.37.32%20PM.png)
#
# Write a program that displays all the alphabets that have almost the same width and height
#
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.37.51%20PM.png)
#
#
#
# hows an image of a bubble sheet filled for an exam. There are five questions, and for each question, there are four choices.
## Write a program that applies DIP techniques to identify the candidate's answer for each question. Display the output in the format as shown below
* Apply binary thresholding on the grayscale image using OpenCV's cv2.threshold() function. This creates a binary image where all pixels above a certain threshold value are set to white (255), and all pixels below the threshold are set to black (0). The thresholded image is stored in the thresh variable.
* Find contours in the thresholded image using OpenCV's cv2.findContours() function. Contours are the boundaries of objects in an image. The contours and hierarchy information are stored in the contours and hierarchy variables, respectively.
* Filter the contours based on their area. The code removes all contours with an area less than 10000 or greater than 15000 pixels. The filtered contours are stored in the filtered_contours list.
* Sort the filtered contours based on their y-axis position using the sorted() function and the key parameter with the cv2.boundingRect() function.
* Group the filtered contours that have y-coordinates within a certain range. The code creates a list of lists, where each sublist contains contours that are close together on the y-axis.
* Sort the contours in each group based on their x-axis position using the sort() function and the key parameter with the cv2.boundingRect() function.
* Find the contour with the maximum filled area within each group. The code iterates through each group and checks each contour to see if it is filled. If a contour is more than 65% filled, it is added to the filled_contours list, and its corresponding option is added to the correct_options list.
* Draw the filled contours on a copy of the original image using OpenCV's cv2.drawContours() function. The copy of the image with the contours drawn on it is stored in the img_copy variable.
* Print the correct option for each filled bubble found by iterating through the correct_options list and using the alphabats string to map the option number to a letter. The output is printed to the console.
#
![output](https://github.com/MSaadMakhdoom/Computer-vision-Digital-Image-Processing-Object-detection-using-Morphological-Operations-Contour/blob/main/output/Screenshot%202023-06-05%20at%206.38.39%20PM.png)
