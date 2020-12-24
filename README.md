# Streaming-a-video-inside-a-TV-image-or-video

In many televised sports events, advertisements is inserted virtually in live video which is know as virtual advertising.  This technique is often used to customise advertisements according to the geographic location of regions. 

I am showing here how to use such technique, firstly by inserting video inside an image and then inserting a video inside another video.

## Extracting screening area or showing area
The code allows you to select tv screen using two different methods, which are:
### 1. Replacing green screen
Most virtual advertising use a green screen to replace it with a designated ad. the function used for that is find_greenScreen(). It takes image or video frame as an input and returns the original image with a masked screen, and mask image in black and white.
### 2. Drawing tv screen 
You can draw tv screen by clicking on its border points.

## Locating screen area
After extracting showing area, call get_contours() function. the function takes the mask image in black & white and return the coordinates of the screen in a clockwise order.

## 1. Insert image inside tv screen image
After loading screen image and input image, call find_greenScreen() function by giving screen image as an input, and then call get_contours() function giving the returned masked as an input. The input image the warped and masked to the screen area after calculating the transformation matrix.

## 2. Insert video inside tv screen image
Load input video and screen image.  call find_greenScreen() function by giving screen image as an input, and then call get_contours() function giving the returned masked as an input. While the input video is running, warp and mask each frame to the screen area.

## 3. Insert video inside video
Load input video and screen video. While screen video is runnig, call find_greenScreen() function by giving each frame as an input, and then call get_contours() function giving the returned masked as an input. While the input video is running, warp and mask each frame to the screen area.
