二叉搜索树
    当前节点的左子树中的数均小于当前节点的数；
    当前节点的右子树中的数均大于当前节点的数；
    所有左子树和右子树自身也是二叉搜索树。

    左中右遍历就是一个递增序列 ，右中左遍历则相反

两个有序集合并归方法
    双指针分别指向不同集合
    逐个比较插入到第三集合直到两指针中某一指针为空
    将剩下非空指针所指剩下所有元素都插入到第三集合

