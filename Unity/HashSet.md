hash表
    常数时间复杂度的查找（O(1)）
    元素不能重复。如果尝试 ***添加重复的元素，它将被忽略***。
    ***插入顺序不会被保持***，迭代时的顺序与插入顺序无关。

+ 定义
    ```
    HashSet<int> numbers = new HashSet<int>();
    HashSet<int> set1 = new HashSet<int> { 1, 2, 3 };

    //去重list中元素
    //实际 HashSet<T> 可以接受任何实现了 IEnumerable<T> 接口的数据结构 如 Array、Queue、Stack 等
    List<int> listWithDuplicates = new List<int> { 1, 2, 2, 3, 4, 4, 5 };
    HashSet<int> uniqueSet = new HashSet<int>(listWithDuplicates);
    ```

+ 增删查 没有 改
    ```
    HashSet<int> numbers = new HashSet<int>();
    numbers.Add(1); //没有1添加成功返回true 列表中存在并添加失败返回false
    numbers.Remove(1);//有1并移除返回true 不在集合中则返回false

    bool contains = numbers.Contains(1);  // 返回 false，因为 1 已被删除 否则返回true
    ```

+ 集合间的操作方法 并集、交集、差集
    ```
    HashSet<int> setA = new HashSet<int> { 1, 2, 3, 4 };
    HashSet<int> setB = new HashSet<int> { 3, 4, 5, 6 };

    // 并集
    setA.UnionWith(setB);  // setA = { 1, 2, 3, 4, 5, 6 }

    // 交集
    setA.IntersectWith(setB);  // setA = { 3, 4 }

    // 差集 从 setA 中删除所有在 setB 中存在的元素,返回在 setA 中有，但在 setB 中没有的元素。
    setA.ExceptWith(setB);  // setA = { 1, 2 }
    ```