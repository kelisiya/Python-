# 基于Python3实现人脑网络链接系统

* * *

# 项目工作

- 基于NetworkX库实现相关方法：
   - 具有社团结构的网络
   - 富俱乐部系数
   - 协同性
   - 中心性度量
   - 最大块模块度
   - 子图中心度
   - 网络动态特性和扰动的度量
  
- 基于pyqt5库实现系统的整合：
	- 搭建前台系统	
	- 实现各个按钮和系统方法的连接
	- 返回结果
* * *

# 更新日志

## 2016.12.05
### 实现了下拉菜单的操作 [代码链接](https://github.com/kelisiya/Python-brains/blob/master/python%20brain/pyqt_test1.py)

## 2017.3.30
- ### 具有社团结构的网络(Networks with Community Structure)：
   - 定义：对于一个图G而言，如果其中有一个完全子图（任意两个节点之间均存在边），节点数是k，那么这个完全子图就可称为一个k-clique。进而，如果两个k-clique之间存在k-1个共同的节点，那么就称这两个clique是“相邻”的。彼此相邻的这样一串clique构成最大集合，就可以称为一个社区，且社区是可以重叠的；
   - NetworkX库：k_ clique_ communities(G, k, cliques=None)[sorce](https://networkx.github.io/documentation/networkx-1.10/_modules/networkx/algorithms/community/kclique.html#k_clique_communities)
   - 说明：Find k-clique communities in graph using the percolation method.
   - 参数说明：
		   - G:图（这里使用的是无向）
		   - k：整型变量，最小团块的大小
		   - cliques ： 预计算派系 
   - 举例：
			
			>>>import networkx ax nx
			>>>import matplotlib.pyplot as plt
			>>> G = nx.complete_graph(5) #返回具有N个节点的完整图，节点标签为0~n-1
			>>> K5 = nx.convert_node_labels_to_integers(G,first_label=2)
			>>> G.add_edges_from(K5.edges())
			>>> c = list(nx.k_clique_communities(G, 4))
			>>> list(c[0])
			[0, 1, 2, 3, 4, 5, 6]
			>>> list(nx.k_clique_communities(G, 6))
			[]
			>>>nx.draw(G) #画出图G
			>>>plt.show() #显示图像

