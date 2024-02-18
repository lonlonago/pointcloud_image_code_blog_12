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

