
曲面细分，英文称Tessellation，如果直译的话应该译作“镶嵌化处理技术”。由ATI开发，微软采纳后将其加入DirectX 11，成为DirectX 11的组成部分之一。由于这种技术广泛的应用在曲面的几何处理上，因此国内翻译时通常译作“曲面细分”。但实际上，这种技术不是只能用在曲面的细分处理上。

Catmull-Clark细分是一种四边形网格的细分法则，每个面计算生成一个新的顶点，每条边计算生成一个新的顶点，同时每个原始顶点更新位置。下图为Catmull-Clark细分格式的细分掩膜，对于新增加的顶点位置以及原始顶点位置更新规则如下：

1.网格内部F-顶点位置：

　　设四边形的四个顶点为v0、v1、v2、v3，则新增加的顶点位置为v = 1/4*(v0 + v1 + v2 + v3)。

2.网格内部V-顶点位置：

　　设内部顶点v0的相邻点为v1、v2，…，v2n，则该顶点更新后位置为，其中α、β、γ分别为α = 1 - β - γ。

3.网格边界V-顶点位置：

　　设边界顶点v0的两个相邻点为v1、v2，则该顶点更新后位置为v = 3/4*v0 + 1/8*(v1 + v2)。

4.网格内部E-顶点位置：

　　设内部边的两个端点为v0、v1，与该边相邻的两个四边形顶点分别为v0、v1、v2、v3和v0、v1、v4、v5，则新增加的顶点位置为v = 1/4*(v0 + v1 + vf1 + vf2) = 3/8*(v0 + v1) + 1/16*(v2 + v3 + v4 + v5)。

5.网格边界E-顶点位置：

　　设边界边的两个端点为v0、v1，则新增加的顶点位置为v = 1/2*(v0 + v1)。
  
  Doo-Sabin细分算法是二次均匀B样条曲面二分技术的推广。不同于Loop细分算法,Doo一Sabin细分算法是一种基于四边形控制网格的细分算法。

    对于初始控制网格中的每个面,新的面可以通过连接该面的所有新顶点得到.
    
    对于初始控制网格中的每条边,连接该边左右面相应的新顶点生成新的面.
    
    对于初始控制网格中的每个顶点,连接相交于该顶点的所有面相应的新顶点生成新的面.
    
    算法见图示。

