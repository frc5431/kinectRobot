# kinectRobot
Using kinect to possible identify target on field and as a vision camera for the FRC 2016's Stronghold

To figure out where things are - 
ColorBasics.cpp has the actual main loop (actually a WINMAIN, since it is windows)
ColorBasics.h has the header for the ColorBasics class (which is the application's class)
ImageRenderer.cpp has the area where it takes the bitmap buffer and processes it.
ImageRenderer.h has the header where it holds the ImageRenderer class's variables and functions.
UDP.h has the entire code needed to do UDP sending.

**Functions to look at**:
- ProcessColor() in ColorBasics.cpp. Processing the image (verifying height, width, etc.) is done here. Most variables and sending that I am doing are in ColorBasics and used in ProcessColor + the ColorBasics constructor
- ImageRenderer.cpp. This is how it displays the image (called from ProcessColor()). It also converts the BGRA (**not RGB**, sorry!) image into a bitmap, which I could potentially use.
- Sento() in the UDP.h code is where the size error happens - because it can't send that much.
