如何实现树的层次遍历 BFS
    两个LIST 或者 两个Queue

    用一个集合去存储当前层 一个集合去遍历当前层节点并保存下一层节点，然后做集合赋值就能完成向下的层次遍历

    实际上是两个循环，第一层循环目的是遍历所有层， 第二层循环目的是 遍历当前层所有节点 去得到下一层的节点

深度优先遍历 DFS
    递归遍历就完事儿了 记得穿layer

