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

