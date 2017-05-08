Nick Mariano - Project 1 Writeup - Udacity Self Driving Car Course

1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

This project took a lot of time for me to complete. It took a very long time for me to understand how each function worked and how each parameter within the function modified the image. I made a lot of errors along the way, but I was able to learn from each one and tune each parameter so that an  image could enter the pipeline and the lane lines could be detected.

My pipeline consists of seven main steps. The first step is to read in the image and turn it to grayscale. Step two is to apply gaussian smoothing (I applied a kernel size of 5). Step 3 is to use Canny edge detection. Then for step four, I created an image mask in the shape of a trapezoid to focus only on the lane lines. The next step was to detect the lines using hough transform. Step six was to draw lines on a blank image, and step seven was to add the image with the colored lines to the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first finding the slopes of the lines. I knew that if the slope was positive, it belonged on the left lane line, and if it was negative, it belonged on the right. Next I used the averages of the points and slope on each side to find b (in y=mx+b). Once I had b, I was able to find the x values for the ‘best-fit-line”.  I knew my y values were just constants. With both x and y values, I was able to plot each of the two lines on the picture using the draw_lines() function.

2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen if there was low light. The computer vision may have difficulty recognizing the lines in the darkness. Another issue would be unfavorable weather. In a rainstorm or hailstorm, the falling rain/hail may interfere with the program being able to recognize lines. Snow is also an obvious concern too. Our software won't work if there are no lane lines on the road.

3. Suggest possible improvements to your pipeline

I thought this project was a very helpful way to introduce us to computer vision. I struggled a bit to get the proper software installed on my machine, but my mentor Vidyasagar was extremely helpful and worked with me until my environment was ready to go! 

One idea for improvement would be a way to tell the pipeline to look for the lane lines in the same place as the last image. The line lines for each sequential image will be relatively in the same location, so we could reduce operations and functions by just looking in the same general area. I could also continue to improve the parameters to draw more consistent lines on each of the images. 
