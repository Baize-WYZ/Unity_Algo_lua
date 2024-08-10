
自动属性（下述等价）
    private string _Title; 
    public string Title{get { return _Title; }set { _Title = value; }}

    完全等价于
        public string Title { get; set; } 

初始化器（用于初始化类的特性
    　var myObj1 = new MyObj ("allen") { id = Guid.NewGuid(), Title = "allen" };
    以及 　var arr = new List<int>() { 1, 2, 3, 4, 5, 6 };

扩展方法（少用）
    为一个类拓展行为，通过非继承方式

            public static void PrintString(this String val)
        　　{
            　　Console.WriteLine(val);
        　　}
        为string 类添加一个新方法 PrintString。之后声明的所以string变量都可以调用该方法。

    扩展方法必须在一个非嵌套、非泛型的静态类中定义
    扩展方法必须是一个静态方法
    扩展方法至少要有一个参数（指名拓展的静态类），且第一个参数必须附加this关键字作为前缀
    第一个参数不能有其他修饰符（比如ref或者out）
    第一个参数不能是指针类型
    如果原来的类中有一个方法，跟你的扩展方法一样（至少用起来是一样），那么你的扩展方法奖不会被调用，编译器也不会提示你

LINQ
    在c#中的”Sql“，语法类似，功能类似。用于从数据库、程序对象的集合以及XML文档中查询数据。

    对象：只要是继承 IEnumerable的对象都可用

    1.Where 
    用于筛选过滤集合内元素。现有 digit = new list<string>();（集合对象都同理
        1)digits.Where((digit, index) => digit.Length < index);
            参数为Func<String,int,bool> 即第一个是value 然后是idx 最后是逻辑表达式值
        2）digits.Where((digit) => digit.Length < 5 )
            参数为Func<String,bool> 即第一个是value 最后是逻辑表达式值

    2.Select
    对集合每个元素或者每个元素的某个子元素做映射，得到新的映射集合。如果要特定元素做映射的话需要配合where（划重点 逐元素都会调用 Select后面的式子作为新集合中的元素）（实际上也有像上述where一样的使用形式
        1）var numsPlusOne = from n in numbers select n + 1;
            numsPlusOne中的每个元素都是numbers中对应元素+1
        2）var productNames = from p in products select p.ProductName;
            选择 products中每个元素的ProductName作为一个新集合
        3）var textNums = from n in numbers select strings[n];
            用numbers中每个元素作为idx去strings中取值作为新集合
        4）var upperLowerWords = from w in words select new { Upper = w.ToUpper(), Lower = w.ToLower() };
            新集合每个元素为匿名类型。这样可以为原集合做信息拓展等操作。
        5）var numsInPlace = numbers.Select((num, index) => (Num: num, InPlace: (num == index)));
        6）var lowNums = from n in numbers where n < 5 select digits[n];
            配合where
        7）var pairs = from a in numbersA from b in numbersB where a < b select (a, b);
            复数from 类似使用for for循环嵌套，会循环遍历两个集合
        8）var orders = from c in customers where c.Region == "WA" from o in c.Orders where o.OrderDate >= cutoffDate select (c.CustomerID, o.OrderID);
            嵌套from中使用过滤器 where
        9）customers.Where((value)=> true).Select((value, idx) => new { index = idx, val = value });
        
        
    