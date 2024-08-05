1.string 为引用类型，但是具有不可变性。从第一次赋值后，在做任何改变都会重新赋值一份修改后再赋值。
2.常用接口
    1）public static int Compare( string strA, string strB , bool ignoreCase)，将两字符串逐字符用ascii值做减法 ，A的字符大返回1，B的字符大返回-1 否者0.ignoreCase用于是否区分大小写
    2）public static string Concat( string str0, string str1 ，...) 连接多个字符串
    3）public bool Contains( string value ) 是否包含value
    4）public void CopyTo( int sourceIndex, char[] destination, int destinationIndex, int count )，复制字符串到char[]
            string str = "abcdefg";
            char[] arg = new char[9] { 'm', 'n', '\0', '\0', '\0', '\0', '\0', '\0', '\0' };
            str.CopyTo(0, arg, 2, 7);
            string rets = new string(arg);
            Console.WriteLine(rets);
        then return mnabcdefg
    5）public bool EndsWith( string value ) 检查字符串结尾是否有value
            string str1 = "Hello, world!";
            string suffix = "world!";
            bool result = str1.EndsWith(suffix);
        then return true

        public bool StartsWith( string value )检查字符串开头是否有value
    6）public string Insert( int startIndex, string value ) 指定位置的插入
    7）public static bool IsNullOrEmpty( string value ) 字符串判空
    8）public static string Join( string separator, string[] value ) 用 separator去连接value中每个字符串）（如果value.length <= 1 不连接
    9）public string Remove( int startIndex, int count ) 移除
    10）public string Replace( char oldChar, char newChar ) 替代所有字符oldChar为newChar
        public string Replace( string oldValue, string newValue )替代所有字符串oldValue为newValue
    11）public string[] Split( params char[] separator )
            string str = "one,two;three four|five";
            char[] separators = new char[] { ',', ';', ' ', '|' };
            string[] result = str.Split(separators);
        result = {one，two,three,four,five}
    12）public string Trim() 移除当前 String 对象中的所有前导空白字符和后置空白字符。
    13）public string ToLower() ToUpper() 大小写转换
    14）public char[] ToCharArray() 转化string为char[]

