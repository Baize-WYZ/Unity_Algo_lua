# 是什么 #

readonly 字段：值可以在运行时通过构造函数或静态构造函数设置，适用于需要运行时赋值且不可变的情况，如配置值、从外部源（如数据库）获取的值等。

const 常量：值在编译时确定，适用于常量值不会变化的情况，如数学常量、默认配置等。

# 区别 #

const 在编译时候就确定了 同时会将该值替换到所有引用了的地方，是隐式static属于一个类而不是实例。与使用普通常量无区别。在跨程序集时候 const 需要重新编译 否则可能出现值不一致的问题 

readonly 可以在运行中确定（构造函数中），或者在定义时候确定，就相当于不能修改的变量，可以是static也可以是实例字段。就是一个变量字段，跨程序集不会出现const的问题

# 语法 #

```c#
public const int MaxItemsConst = 100;

// 运行时常量
public readonly int MaxItemsReadonly;

public Example(int maxItems)
{
    MaxItemsReadonly = maxItems;  // 通过构造函数赋值
}
```