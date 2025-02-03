数组模拟字典Dictionary<char,int> 存放字符顺序/字符hash表

    int[] charOrder = new int[26];
    for (int i = 0; i < order.Length; i++){
        charOrder[order[i] - 'a'] = i;
    }

    取值时候同样用 order[i] - 'a'方式找到对应的值（也就是顺序）