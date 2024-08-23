char struct
1.提供为  UTF-32 码点 和 Unicode 字符转换的接口

2.提供 char 转换为 double类型的转换接口（如果char不代表数字则返回-1）
    public static double GetNumericValue(string s, int index);
    public static double GetNumericValue(Char c);

3.提供 识别char是何种类型（大小写，标题字母，十进制数字，占位符号等等） 
    public static UnicodeCategory GetUnicodeCategory(Char c);
    public static UnicodeCategory GetUnicodeCategory(string s, int index);
        UnicodeCategory 枚举类型，指明字符类型。
        相较与 Char.GetUnicodeCategory（）来说 CharUnicodeInfo.GetUnicodeCategory(Char)更加稳定。有时前者对同一个char不一定会返回同一个UnicodeCategory

4.提供 char 的类型判断
    控制字符：char.IsControl(Char c)
    十进制数字字符：char.IsDigit(Char c)
    数字字符：char.IsNumber(Char c)
    字母字符：char.IsLetter(Char c)
    小写字母字符：char.IsLower(Char c)
    大写字母字符：char.IsUpper(Char c)
    标点字符：char.IsPunctuation(Char c)
    分隔字符：char.IsSeparator(Char c)
    空白字符：char.IsWhiteSpace(Char c)

5.提供 char的字符转换
    大小写间转换

    字符串 到char的转换（只处理长度为 1 的字符串并返回对应的字符）