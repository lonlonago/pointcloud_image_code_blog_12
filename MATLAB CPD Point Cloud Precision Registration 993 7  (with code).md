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

