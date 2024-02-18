#  I. Introduction 

Matlab version is 2022. 

>  STL data: This file is a model file format created by 3D Systems, which is mainly used to represent triangular meshes, mainly used in CAD and CAM fields. STL can only be used to represent closed surfaces or volumes functionally, and there are two file formats: text and binary. The first line of the text format STL file gives the file path and file name, and the following line gives the geometric information of the triangular face piece line by line. Each line starts with 1 or 2 keywords. The STL file format organizes data in units of triangular facets, and each triangular facet consists of 7 lines of data: facet normal is the normal vector coordinate of the triangular facet pointing to the outside of the entity, and outer loop indicates that the subsequent 3 lines of data are the 3 vertex coordinates of the triangular facet, and the 3 vertices are arranged counterclockwise in the direction of the normal vector pointing to the outside of the entity. The last line is the end flag. 

>  PLY data: A polygon file format designed and developed by Turk and others at Stanford University, and therefore also known as the Stanford Triangle format. File formats are available in both text and binary formats. A typical PLY object definition is simply a list of (x, y, z) triples of vertices and a list of faces described by the index in the vertex list. The file structure is as follows: 

· Header · Vertex List · Face List · (lists of other elements) 

MatLab can also load the format directly through the pcread function. 

#  Implementation code 

>  Stl file read and write: 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574083913
 ```  
>  PLY file read and write: 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574083913
 ```  
#  III. Achieving results 

![avatar]( 684f825d4d4740a8aafbc7d1b73f2988.png) 

 ![avatar]( 2d5c8840cb4d400c9cfdb6af31474b0e.png) 

 ![avatar]( f1a1ebb8995246bba3435c93c3dfb7c8.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The principle of this method is relatively simple, that is, by fitting a cylinder through the trunk points, all the points of the point cloud are projected to the axial direction of the cylinder, and then the height of the tree can be obtained by obtaining the maximum and minimum value of the axial projection. 

#  Implementation code 

>  ExtractStemAndHeight.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957405434
 ```  
>  ROR.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957405434
 ```  
#  III. Achieving results 

![avatar]( 6347ac748ce04796a4cd4992ea563ea0.png) 

 ![avatar]( b9c77150c3c641699c9d00e4590dc66e.png) 



--------------------------------------------------------------------------------

#  I. Introduction 

Azimuth refers to the horizontal angle of rotation clockwise from the due north direction of a certain point to the direction of a certain target point, and the angular range is (0 °~ 360 °). As follows: 

![avatar]( c08d2439f3f74ffb9266e52cecf9e97b.png) 

>  Let atn = 

          a 

          r 

          c 

          t 

          a 

          n 

          ( 

          W 

           Y 

            A 

            B 

          / 

          W 

           X 

            A 

            B 

          ) 

         arctan (\Delta{Y}_{AB}/Delta{X}_{AB}) 

     arctan(ΔYAB​/ΔXAB​)，dx =  

          W 

           X 

            A 

            B 

         \Delta{X}_{AB} 

     ΔXAB ,dy =  

          W 

           Y 

            A 

            B 

         \Delta{Y}_{AB} 

     Delta YAB is easy to derive: 

1. When 

           a 

            A 

            B 

         \alpha_{AB} 

     When α AB is in the first quadrant, dy > 0, atn > 0, 

           a 

            A 

            B 

         \alpha_{AB} 

     αAB = 90°- atn =180°-90°- atn =180°-90°sgn (dy) - atn; 

           a 

            A 

            B 

         \alpha_{AB} 

     Alpha AB in the second quadrant dy > 0,  

           a 

            A 

            B 

         \alpha_{AB} 

     αAB​=atn; 3、当 

           a 

            A 

            B 

         \alpha_{AB} 

     Alpha AB in the third quadrant dy < 0,  

           a 

            A 

            B 

         \alpha_{AB} 

     α AB = 180 ° + (90 ° - atn) = 180 ° + 90 ° - atn = 180 ° -90 ° sgn (dy) - atn; 4. When α is in the fourth quadrant, if dx = 0, dy  

          ≠ 

         \ if 

     = 0， 

           a 

            A 

            B 

         \alpha_{AB} 

     αAB = 180°-90°sgn (dy) - atn = 90° കുറ者270°;  

          ± 

         \pm 

     ± 90°， 

           a 

            A 

            B 

         \alpha_{AB} 

     αAB = 180°-90°sgn (dy) - atn=0° 

>  To sum up: 

           a 

            A 

            B 

         \alpha_{AB} 

     αAB = 180°-90°sgn (dy) - atn。 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574024101
 ```  
 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574024101
 ```  
#  III. Achieving results 

![avatar]( 566f57cb3b0c4ef284919d55aaa0ed7a.png) 

 ![avatar]( 0b8300966d0941d5a9ff93b94c57b325.png) 

 ![avatar]( 99d0916bf9424bf89c8ab65ce520a3a7.png) 

 ![avatar]( 1c2d51f3aa724325b528a8f9f489c772.png) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Boundary (MATLAB built-in function) constructs an alphaShape based on specified points, and then uses boundaryFacets to determine which points are located on the boundary. 

#  Implementation code 

>  BoundaryV1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574056016
 ```  
#  III. Achieving results 

![avatar]( cbe6de6c9d9a4abfb0b1e891311dc3a2.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  There are many sorting algorithms for single-profile data points, the simplest of which is the search algorithm based on the nearest point. The idea of the closest point search algorithm is to select a point as the starting point, search for the point closest to the starting point in the remaining points, and record it as the new starting point. Until all the remaining points are searched, the sorting of single-profile data points is completed. 

The previous algorithm had some problems (MATLAB boundary point sorting (nearest neighborhood search algorithm)), which is only suitable for sorting data with relatively uniform boundary point density. Here, modify it and implement it strictly according to the ideas in the paper to reduce the impact of point density on it. 

#  Implementation code 

>  PointSortV4.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574054424
 ```  
#  III. Achieving results 

![avatar]( 1da696a6ee7d4171b949224897b024d5.png) 

 ![avatar]( 0e31857ac2874ad7876680ae0cbe9d30.png) 

#  reference 

>  [1] MATLAB boundary point sorting (nearest neighbor search algorithm) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  There are many sorting algorithms for single-profile data points, the simplest of which is the search algorithm based on the nearest point. The idea of the closest point search algorithm is to select a point as the starting point, search for the point closest to the starting point in the remaining points, and record it as the new starting point. Until all the remaining points are searched, the sorting of single-profile data points is completed. 

#  Implementation code 

>  PointSortV1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574055490
 ```  
MATLAB Boundary Point Sorting (Nearest Neighborhood Search Algorithm 2) 

#  III. Achieving results 

![avatar]( 84391bf4742946318e21fdbc57abee5c.png) 

#  reference 

>  [1] Multi-contour sorting algorithm based on point cloud cross-section data points 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The overall idea of calculating point density is as follows: first project the point cloud, then divide the projection points into grids, count the number of grids containing the projection points, and finally divide the number of points with the statistical area to calculate the out-point density value. 

#  Implementation code 

>  PointDenstity.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574084335
 ```  
#  III. Achieving results 

![avatar]( 9fd62e2861bb4b60a2d95f1b0e7dd012.png) 

#  reference 

>  [1] CloudCompare & PCL calculate point cloud point density (2D) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Suppose a point is located on a curved surface 

          z 

          = 

          f 

          ( 

          x 

          , 

          y 

          ) 

         z=f(x,y) 

     Z = f (x, y), then the slope (S) at that point will be defined as a function of the layers (i.e. W-E and N-S) directions at X and Y, i.e.: 

>  Among them, 

           f 

           x 

           2 

          、 

           f 

           y 

           2 

         f_{x}^2、f_{y}^2 

     Fx2, fy2 refers to the layers in the W-E and N-S directions. 

From the above equation, the key to slope calculation is 

           f 

           x 

         f_{x} 

     FX and 

           f 

           y 

         f_{y} 

     There are many ways to calculate fy (as shown in the figure below). When using mesh-based DEM, a common method is to use a moving 3 × 3 window to derive a finite differential or a locally curved surface fitting polynomial for calculation. 

![avatar]( ef618eb9f54e4b8c89366d51094b84b0.png) 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574066544
 ```  
#  III. Achieving results 

![avatar]( 16cc2b204594418fbc50c50b68a7e8e9.png) 

 ![avatar]( 92fcda95948b48c9b7072887e4de5202.png) 

 ![avatar]( fbdb07479fe74e0a94e7e57d1bfbcfb9.png) 

#  reference 

>  [1]Error Analysis on Grid-Based Slope and Aspect Algorithms 



--------------------------------------------------------------------------------

#  I. Introduction 

>  An interesting little feature that calculates the area of any polygon in 3D space: 

![avatar]( 46fb90f0c90048a682c0089f681a2b8b.png) 

 ![avatar]( c543ae54a6924221ba08b27b3a704e8c.png) 

 ![avatar]( e58bb8d749e04e159a8b18a41b4927db.png) 

 ![avatar]( 2c4179c029214d96b3c2f471b3fea95d.png) 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574071815
 ```  
#  III. Achieving results 

![avatar]( 7dedab52211f4333980a64af4daba4aa.png) 

 ![avatar]( cd4d4fe7ed30455c9ac218838528f823.png) 

#  reference 

>  [1]https://blog.csdn.net/weixin_45660006/article/details/107699089 [2]https://github.com/caoguolin/3D-Polygon-area 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  The iterative closest point (ICP) algorithm is the most commonly used rigid point set registration method at present. It has the advantages of simplicity and low computational complexity, but the basic requirement of ICP is that the initial positions of the two point sets need to be close enough, otherwise there may be problems such as large registration errors, and the method will no longer be applicable for some non-rigid transformations. Therefore, in order to overcome these shortcomings, many probability methods have been introduced. These methods use soft allocation of matching points, that is, to establish a match between all combined points according to a certain probability, and generalize the matching mechanism between points and points or points and surfaces in ICP. Among them, CPD (Coherent Point Drift Algorithm) belongs to this class of algorithms. 

#  Implementation code 

>  CPD.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574069920
 ```  
>  For relevant parameter settings, please refer to the MATLAB help documentation (select the function name and press F1). 

#  III. Achieving results 

![avatar]( d60b4dc7a87d476fa1aa4b6dd5bb40ba.png) 

![avatar]( 184d84049d0340caa999d0ce84c5fb00.png) 

#  reference 

>  [1] Myronenko, A., and X. Song. "Point Set Registration: Coherent Point Drift. "Proceedings of IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI). Vol 32, Number 12, December 2010, pp. 2262–2275. [2]Matlab帮助文档（选中函数名按F1） 



--------------------------------------------------------------------------------

#  I. Introduction 

 The principle of this method is very ingenious: the scanned point cloud is inverted, and then the inverted point cloud is covered with a rigid cloth. By analyzing the interaction between the cloth nodes and the points in the corresponding point cloud, the position of the cloth nodes can be determined to generate an approximate surface shape. Finally, by comparing the distance between the points in the original point cloud and the generated fabric surface, the ground points can be extracted from the point cloud entity. The author of this method is Professor Zhang Wuming, and the source code has been uploaded to github. Here is just a demonstration of the usage of its Matlab version plug-in. 

![avatar]( 20200328163646530.png) 

#  Implementation code 

1. First, we need to download the source code, as shown below. 

![avatar]( 4dd899c263b54417ba4cb24bb0700828.png) 

 2. Compile the Matlab version of the CSF plugin. 

![avatar]( 2fb691941daa40de8a8c95bba2859dda.png) 

 ![avatar]( c15527b9900e4beeba338074dfb6f9f7.png) 

 3. Create a script and use the plugin. 

![avatar]( 06ac07dbc2ff4791bb8af7475005e0de.png) 

>  CSF.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574033732
 ```  
#  III. Achieving results 

![avatar]( f66425c263b041f98b2a03b30afbbefc.png) 

 ![avatar]( 22767c5f56ed4f5c8fa8a8602968e7a1.png) 

 ![avatar]( 0e6883935c7747c492dc526f7b007f5b.png) 

#  reference 

>  [1] Point cloud ground point filter (CSF) "cloth" filtering algorithm introduction [2] https://gitcode.net/mirrors/jianboqi/CSF?utm_source=csdn_github_accelerator 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Definition: In a statistical unit, all the normalized lidar point clouds within it are sorted by height and the cumulative height of all points is calculated. The cumulative height of X% of the points in each statistical unit is the cumulative height percentile of the statistical unit. 

#  Code implementation 

>  POH.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574076725
 ```  
#  III. Achieving results 

![avatar]( 593c4c5d233d49d196f0202a70c2c687.png) 

#  reference 

>  [1]https://www.lidar360.com/wp-content/LiDAR360-zh/ToolReference/ALSForest/TheoryOfElevationMetrics.html 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The previous blog has done this content (judging whether a point is inside a polygon), but today I saw another way, which is very interesting, and I realized it. The specific idea is very simple, that is, through the normal vector of each side of the polygon to determine whether the point is inside or outside the polygon. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574022449
 ```  
#  III. Achieving results 

![avatar]( 0e0046a67be9470ab4dc0d3f817fdb3e.png) 

 ![avatar]( 1c878fb0aaa44c3d9cf742198bc9221f.png) 

#  reference 

>  [1]Geometric Tools for Computer Graphics 



--------------------------------------------------------------------------------

#  I. Introduction 

##  1.1 Overview 

>  When obtaining a point with the same name from multiple views, an indispensable process is to use polar geometry to solve its three-dimensional space position. In simple terms, polar geometry is the intrinsic projective geometry between two views. It does not depend on the scene structure, but only on the internal parameters and relative poses of the camera. 

>  Here are two views as an example: The polar geometry between the two views is essentially a geometric problem where the plane with the baseline as the axis (the baseline is the line connecting the center of the camera) intersects the image plane. This geometry is usually driven by looking for the corresponding point in the stereo matching image. Suppose a point in three-dimensional space 

          X 

         X 

     X is imaged in two views, the first is in 

          x 

         x 

     Point x, the second one is at 

           x 

           ′ 

         x' 

     X ′ point. Corresponding image point 

          x 

         x 

     X and 

           x 

           ′ 

         x' 

     What is the relationship between x ′? As shown in the image below, the image points 

          x 

          、 

           x 

           ′ 

          Space point 

          X 

         X, x ', space point X 

     X, x ′, space point X is coplanar with the center of the camera. Use 

          i 

         i 

     Pi represents this plane. Obviously, in 

          i 

         i 

     Within pi, 

          x 

         x 

     X and 

           x 

           ′ 

         x' 

     X ′ s reflected rays intersect at 

          X 

         X 

     When looking for a correspondence, the latter property is most important. 

![avatar]( 9933dd6586f8408db2e7eefd5f35439c.png) 

>  Suppose now we only know 

          x 

         x 

     X, then the corresponding point 

           x 

           ′ 

         x' 

     How is x ′ constrained? plane 

          i 

         i 

     Pi is determined by the baseline and 

          x 

         x 

     X is defined by the ray, from which we know the (unknown) point 

           x 

           ′ 

         x' 

     X ′ The corresponding ray is in 

          i 

         i 

     On pi, therefore 

           x 

           ′ 

         x' 

     X ′ is located in 

          i 

         i 

     The intersection of π with the second imaging plane 

           l 

           ′ 

         l' 

     L ′ on. This line 

           l 

           ′ 

         l' 

     L ′ is the ray from 

          x 

         x 

     X backprojection of the image in the second view, which is 

          x 

         x 

     The polar line corresponding to x. For the stereo correspondence algorithm, the advantage is that the search and  

           x 

           ′ 

         x' 

     The corresponding points of x ′ do not need to cover the entire image plane and can be limited to straight lines 

           l 

           ′ 

         l' 

     L ′ Inside. 

![avatar]( 03cbca43bc64441c9b4cad07686aafc2.png) 

 ![avatar]( 7777e1b73d24468194d9af82675206e3.png) 

##  1.2 Eigenmatrix and fundamental matrix 

>  Given a pair of images, as can be seen from the graph above, at each point in an image 

          x 

         x 

     X, there is a corresponding pole line in the other image 

           l 

           ′ 

         l' 

     L ′, the second image with the point 

           x 

           ′ 

         x' 

     Any point that x ′ matches 

          x 

         x 

     X must be at the pole 

           l 

           ′ 

         l' 

     So there will be a mapping relationship (point-to-line, that is, from a point in one image to the corresponding polar line in another image). We will find that this mapping is a (singular) correlation, which is a point-to-line projection mapping. The mapping process can be divided into two steps: 

>  It can ultimately be composed of a fundamental matrix 

          F 

         F 

     F means. 

>  Next, let's think about it. The antipolar geometry of two views is ultimately used to solve the attitude changes (translation and rotation) of one view (right) relative to the other view (left). 

          t 

          、 

          R 

         t、R 

     T, R), as shown in the following figure: 

![avatar]( 89b393eda16949a1bd8ec40a8e3ed5f9.png) 

>  among them 

           x 

           l 

         x_l 

     XL is the point 

          P 

         P 

     P to left camera center 

           O 

           l 

         O_l 

     Ol's vector, 

          t 

         t 

     T is the center of the right camera. 

           O 

           r 

         O_r 

     Or to 

           O 

           l 

         O_l 

     The translation vector of Ol, therefore the normal vector of the Epipolar Plane 

          n 

         n 

     N can be expressed as 

          t 

          × 

           x 

           l 

         t×x_l 

     T × xl. Naturally you get: 

>  We can use this condition as a constraint on the limit and write it in the form of a vector: 

![avatar]( 8fd67a98988b4e9b8290827e57570296.png) 

>  Continue to expand into matrix vector form: 

![avatar]( 87a30c861647454fb90f1f5ca6746d60.png) 

 Note that where t is the position vector between the center of the right camera and the center of the camera, and R is the rotation transformation from the right camera to the left camera. Therefore, we can get: 

![avatar]( 09501f79a3654e518c80312af5da67f5.png) 

 ![avatar]( 81e646c6fd444952858d20054422f514.png) 

>  Since the last item is the multiplication of the translation matrix by the translation vector, it is equal to the cross product of two translation vectors, therefore equal to 0. After some changes, we can obtain: 

![avatar]( 05104d0d925a4956ab955ba4654f95d3.png) 

 ![avatar]( d40b80a2d7e343ff83a1eac7208f3f00.png) 

>  among them 

          E 

         E 

     E is the so-called eigenmatrix, which is the product of the translation matrix and the rotation matrix. Since one of the two matrices is a partial symmetric matrix and the other is an orthogonal matrix, the SVD decomposition can be used based on the properties of the two matrices 

          E 

         E 

     E matrix to obtain both. 

>  OK, so far our problem starts from solving 

          t 

          、 

          R 

         t、R 

     T, R become the solution 

          E 

         E 

     E-matrix, but a big problem is that we don't understand the point 

          P 

         P 

     The three-dimensional coordinate position of P in the left and right cameras (i.e. 

           x 

           l 

          with 

           x 

           r 

         x _ lensx _ r 

     XL and XR), as follows: 

![avatar]( 0f509c1836064eeb9857248f22dd267d.png) 

>  Although that is the case, we actually have the projection point of that point in both images, taking the perspective projection of the left camera as an example: 

![avatar]( 010cec6e0ba045aab7ec462411305273.png) 

>  Expressed in the form of a matrix: 

![avatar]( 391b869ce52540fcbb86325b49b0484a.png) 

>  Therefore, we can also obtain the three-dimensional positions of the corresponding points in the two cameras, which can be expressed as: 

![avatar]( 76e7535d8d874336b48d21a8c319edb6.png) 

>  The previous polar constraint equation can be changed to: 

![avatar]( 9c17d6ea9db34057af9a817a75eeb009.png) 

>  And because of this 

           z 

           l 

          、 

           z 

           r 

         z_l、z_r 

     Zl and zr are expressed as the depth distance from the point to the center of the camera, so neither is 0, and we can get: 

![avatar]( c84c7f471a0148a58cf039067236c4ef.png) 

>  Now let's look at the above equation again, 

          u 

          、 

          v 

          、 

          K 

         u、v、K 

     U, v, and K are all known parameters, only 

          E 

         E 

     The E matrix is unknown, change the form: 

![avatar]( bb3ec712d3cc4311b8cdd894e08b0e06.png) 

>  Among them, 

          F 

         F 

     F is the so-called fundamental matrix, which contains the internal parameter matrix of the camera and 

          E 

         E 

     E matrix. 

OK, here we understand how to solve the so-called fundamental and eigenmatrix. First, we need to obtain a set of corresponding points in the image, and then obtain the fundamental matrix based on this 

          F 

         F 

     F, based on 

          F 

         F 

     F, combined with the internal parameters of the camera, we can solve for the eigenmatrix 

          E 

         E 

     E, and finally use SVD decomposition to get what we need 

          t 

          、 

          R 

         t、R 

     T and R parameters. 

#  Give an example 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574019296
 ```  
#  III. Achieving results 

![avatar]( 1484ced3383643cfa83051e2e3f57d63.png) 

 ![avatar]( b6e9f104326f49e5987120dd63a0140c.png) 

 ![avatar]( c24278050c3b44f7b14a2c55cbe096a0.png) 

 ![avatar]( 1487287fd37d4bfd9aff4a1d6b3c9832.png) 

 ![avatar]( ec375e6a98044b38a4244ee3b93af3a9.png) 

 ![avatar]( ecfda3478fae4c43b87d9e64e9fc803b.png) 

#  reference 

>  [1] https://www.youtube.com/watch?v=6kpBqfgSPRc&t=1s [2] Multiple View Geometry in Computer Vision 



--------------------------------------------------------------------------------

#  I. Introduction 

>  For the specific principle of European-style clustering, please refer to the previous article: MATLAB European-style clustering. Here, use MATLAB built-in functions to achieve the clustering effect. It is worth noting that MATLAB's built-in European-style clustering is not the original European-style clustering algorithm. It is improved on the basis of the original algorithm. Its principle is similar to the code in this blog: MATLAB Fast European Clustering (FEC) 

#  Implementation code 

>  EuclideanCluster.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574075517
 ```  
#  III. Achieving results 

![avatar]( 5fe7692d4cb74c0bb5472a16b645c949.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The specific process of European clustering has been said before in this article (https://blog.csdn.net/dayuhaitang1/article/details/123302352?spm=1001.2014.3001.5501), so I will not go into too much detail. The following figure is the official algorithm steps of PCL. The whole process is relatively simple, so it is implemented using MATLAB. 

![avatar]( 4b322f89aacf422098bdcf2814052e71.png) 

#  Code implementation 

>  EuclideanCluster.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574077706
 ```  
#  III. Achieving results 

>  Original data source 

![avatar]( 1e14c33f748d402196b105fc1b0c52b2.png) 

>  Clustering results: 

![avatar]( 31e085453c5547b6b3eed9cc369b745e.png) 

![avatar]( 7b49625e317d420895dff879bff1d4c3.png) 

#  reference 

>  [1]https://pcl.readthedocs.io/projects/tutorials/en/latest/cluster_extraction.html#cluster-extraction 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  The idea of this sampling method is also relatively simple. The specific process is as follows: 1. First, randomly obtain a certain point as a seed point, and obtain the neighboring point set of the seed point, and mark all the points in the neighboring point set. 2. Select the farthest point from the neighboring point set as the next seed point, and add the previous seed point to the sampling point set. 3. Repeat the process of 1~ 2 until all points are marked, then the algorithm stops and the final sampling point set is obtained. 

#  Implementation code 

>  farthestSamplingBySphere.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574033301
 ```  
#  III. Achieving results 

![avatar]( edb880c21ce44fe79c3ccfe20924f36f.png) 

 ![avatar]( 7323feead4834481a31130ad7f39b08a.png) 

#  reference 

>  [1] MATLAB farthest point sampling (FPS improved version) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  In short, this method selects the point farthest from the previous point set by iterative and incremental means to realize the data sampling process. The algorithm steps are as follows: 

![avatar]( 9711abc2752647d3833dabe9bf0be555.png) 

>  (1) From the point set 

          S 

         S 

     randomly select a point in S 

           p 

           i 

         p_i 

     Pi as sample point set 

          X 

         X 

     The first point in X. (2) Compute the distance between the remaining points and the set of sampling points (i.e. each remaining point to the set of sampling points) 

          X 

         X 

     The shortest distance of X), choose the distance from it 

          X 

         X 

     X largest point 

           p 

           j 

         p_j 

     PJ as the new sampling point and add it to 

          X 

         X 

     In X. (3) Repeat the process of (2) until the number of sampling points reaches the requirements set by us, then the sampling process can be stopped. 

#  Implementation code 

>  FPS.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574072013
 ```  
#  III. Achieving results 

![avatar]( 5ed4f6a776134b5aa383f6d038a6e204.png) 

>  However, the process sampling speed of the method I implemented here is a bit slow. Open3D has also implemented this method. Interested students can also try it: Open3D Farthest Point Sampling (FPS). 

#  reference 

>  [1] Automotive LiDAR ground point cloud extraction based on improved RANSAC algorithm 



--------------------------------------------------------------------------------

