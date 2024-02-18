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

