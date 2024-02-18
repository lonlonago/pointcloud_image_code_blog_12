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

