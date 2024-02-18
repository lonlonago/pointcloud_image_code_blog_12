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

