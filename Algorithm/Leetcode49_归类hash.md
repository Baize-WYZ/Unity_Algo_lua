题解：
    字符串数组分组，同一组的str字符长度，字符种类，每种字符出现次数都一致，唯一不一致是顺序。所以考虑去排序，用排好序的为key。做一次hash。


一般用规则去考虑hash的key 在对每个字符用一次规则，去按照key存放在对应组中。