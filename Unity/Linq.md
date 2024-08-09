在c#中的”Sql“，语法类似，功能类似。用于从数据库、程序对象的集合以及XML文档中查询数据。

匿名类型
    1）var student = new { Name = "Mary Jones", Age = 19, Major = "History" };	
        匿名类型只能和局部变量配合使用，不能用于类成员。
        必须使用var关键字作为变量类型。
        不能设置匿名类型对象的属性。编译器为匿名类型创建的属性是只读的。
    2）匿名类型的对象初始化语句另外两种形式：简单标识符和成员访问表达式
        class Other{static public string Name = "Mary Jones";}
        string Major = "History";
        var student = { Age = 19, Other.Name, Major };	// 赋值形式、成员访问、标识符

        当调用student.name 时候就是调用 other的成员访问 即调用 Other.Name

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

迭代器
    