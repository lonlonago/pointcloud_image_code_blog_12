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

