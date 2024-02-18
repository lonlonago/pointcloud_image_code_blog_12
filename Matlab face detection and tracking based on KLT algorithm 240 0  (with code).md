#  I. Introduction 

>  Object detection and tracking are important in many computer vision applications, including activity recognition, automotive security, and surveillance. Here the tracking problem is broken down into three parts: 

>  First, you must detect faces. Matlab uses vision. CascadeObjectDetector objects to detect the position of faces in video frames. Cascaded object detectors use Viola-Jones detection algorithms and trained classification models for detection. By default, the detector is configured to detect faces, but can also be used to detect other types of objects. 

>  Then to track faces over time, the Kanade-Lucas-Tomasi (KLT) algorithm is used. Although it is possible to use a cascaded object detector on each frame, it is computationally expensive. It may also fail to detect faces when the subject turns or tilts their head. This limitation comes from the type of classification model trained for detection. 

>  Determine which facial features to track: The KLT algorithm tracks a set of feature points in a video frame. Once the detection has located a face, the next step is to identify feature points that can be tracked reliably. The following uses the standard "tracked features" proposed by Shi and Tomasi. 

>  After identifying the feature points, you can now use the vision. Use the PointTracker system object to track them, and for each point in the previous frame, the point tracker tries to find the corresponding point in the current frame. Then make the estimateGeometricTransform2D function to estimate the translation, rotation, and scaling between the old and new points, and apply this transformation to the bounding box around the face. 

>  Repeat the above process to each frame in the video to complete the face tracking process. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574035624
 ```  
#  III. Achieving results 

![avatar]( 3fec6aabd0ef4138a16eb68502d76f0b.png) 

 ![avatar]( c6e9310a763544b7ad5fc4217a1671dc.png) 

 ![avatar]( c0dad7b1785d40d4b31621f83eddcafb.png) 

#  reference 

>  [1]https://ww2.mathworks.cn/help/vision/ug/face-detection-and-tracking-using-the-klt-algorithm.html 

