#  I. Introduction 

>  In life, some pinhole cameras can cause serious image distortion, which is mainly due to hardware and environmental factors. The main two types of distortion are radial distortion and tangential distortion. 

>  Radial distortion causes a straight line to appear curved, i.e. the farther the point is from the center of the image, the greater the radial distortion. For example, the following shows an image in which two edges of a chessboard are marked with red lines. But it can be seen that the boundaries of the chessboard are not straight lines, and do not match the red lines, and all expected straight lines bulge out. 

![avatar]( 7cb48cccc77d43edaa466a005a4946d2.png) 

>  Radial distortion occurs when light rays bend more near the edge of the lens than at the center of the optics. 

![avatar]( 61ae31e07e41469dbddb8c8211076d7f.png) 

>  Radial distortion can be expressed as (where k3 is sometimes not required): 

![avatar]( d57efefdcd0d4e1d857bba1ce2d78ee6.png) 

>  Similarly, because the image capturing lens is not completely parallel to the imaging plane, tangential distortion occurs. As a result, some areas in the image may appear closer than expected. The amount of tangential distortion can be expressed as: 

![avatar]( 04be65a6e1f542179fca3a00d7a87867.png) 

 ![avatar]( 68baa55b8cd148ddb5d7d30c3cd48c54.png) 

>  In summary, we need to find five parameters, called distortion coefficients, which are calculated as follows: 

![avatar]( 361946f49c79451780d20583beaee28d.png) 

>  In addition to this, we also need some other information, such as the internal and external parameters of the camera. Intrinsic parameters are camera-specific. They include information such as focal length: 

![avatar]( 2c51612273fa44539d91716fa54423d9.png) 

>  The external parameters correspond to the rotation and translation vectors that translate the coordinates of the 3D points into the coordinate system. 

>  For stereoscopic applications, these distortions need to be corrected first. To find these parameters, we have to provide some sample images with well-defined patterns (e.g. a chessboard). We find some specific points whose relative positions we already know (e.g. the square corners on the chessboard). We know the coordinates of these points in real-world space, and we know the coordinates in the image, so we can solve for the distortion coefficients. To get better results, we need at least 10 test patterns. 

>  Matlab uses the following method to complete the entire correction process: first, the distortion coefficient needs to be calculated (the built-in parameters of the camera are known), and then the photo is corrected based on the mathematical model. The corrected photo is different in size from the original image, and the pixel value is not an integer, so the final image is interpolated using bilinear. 

![avatar]( 6e8a5edea13b47c2b3cf8f8372e3eed8.png) 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574034603
 ```  
#  III. Achieving results 

![avatar]( 7490b2f216174f7685912239cdddcc64.png) 

 ![avatar]( 6daf8bbd411a4933af9195e70356d0b8.png) 

#  reference 

>  [1]https://ww2.mathworks.cn/help/visionhdl/ug/image-undistort.html [2] https://docs.opencv.org/4.x/dc/dbb/tutorial_py_calibration.html 

