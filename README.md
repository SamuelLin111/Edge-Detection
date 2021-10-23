# Edge-Detection

![](Edge-Detection-Examples.png)


This project is to detect edges in images. This could later be used in Image Sharpening. Image Sharpening is when you enhance the definition of edges in a images. 



Edge Detection could be done in four ways. 



Method 1:
In Method 1, you subtract the smoothed image from the original image. To smooth an image, you make each pixel the average of the 8 pixels around it and itself.



Method 2:
![](Method-2-Diagram.png)
In Method 2, each pixel is equal to the absolute value of the bottom left pixel subtracted from the top left pixel added to the top right pixel subtracted from the  bottom right pixel.

pixel = im[x, y]

sum = (im[x - 1, y - 1] - im[x - 1, y + 1])

sum += (im[x + 1, y + 1] - im[x + 1, y - 1])

new_im[x, y] = np.abs(sum)



Method 3:
![](Method-3-Diagram.png)
In Method 3, each pixel is equal to the absolute value of itself subracting the eight pixels around it multiplied by eight.

sum = 8*(im[x, y]) - (im[x - 1, y + 1]) - (im[x - 1, y]) - (im[x - 1, y - 1]) - (im[x, y + 1]) - (im[x, y - 1]) - (im[x + 1, y + 1]) - (im[x + 1, y]) - (im[x + 1, y - 1])

new_im[x, y] = np.abs(sum)



Method 4:
![](Method-4-Diagram.png)
In Method 4, eanch pixel is equal to the absolute value of itslf multiplied by four subracting the four pixels on its right, left, bottom, above.

sum = 4 * im[x, y] - (im[x-1, y] + im[x + 1, y] + im[x, y + 1] + im[x, y - 1])

new_im[x, y] = np.abs(sum)
