# Image-Difference-OpenCV

The background of an image is made transparent by using image subtraction techniques. The steps taken are as below.
-	Read the image without the object (must be a png image).
-	Read the image with the object (must be a png image).
-	Use the OpenCV function (cv2.absdiff(img1, img2)) to get the absolute value of the result of subtracting the two images.
-	Convert the color of the resulting image to BGRA to have 4 channels (Blue color, Green color, Red color, and Alpha for opacity or transparency).
-	Create a mask that will exchange each pixel in the background to the BGRA value (0, 0, 0, 0) where Alpha = 0 which means transparent.
-	If the value of the background is known, we assign it to the (bg_color) variable, otherwise if it is a single value, we can take it from the image array assuming that pixel (0,0) would have the value of the background color, else if the background has multiple values, mostly dark gray to black, up to [50, 50, 50]), we create a mask for each pixel that varies as (B= 0 -> 25, G= 0 -> 25, R= 0 -> 25) using three-level nested for loop for each color. Also, I have tried (B= 0 -> 50, G= 0 -> 50, R= 0 -> 50) to get a better result but it would take more time. 


![imgs](https://user-images.githubusercontent.com/40549682/63403968-1561b800-c3ea-11e9-92bf-3d512040a7a4.PNG)

## Result:

![src](https://user-images.githubusercontent.com/40549682/63404061-6bcef680-c3ea-11e9-997f-3dcdb394c770.png)

![out](https://user-images.githubusercontent.com/40549682/63404043-52c64580-c3ea-11e9-89a3-9cbacba47a2b.png)
