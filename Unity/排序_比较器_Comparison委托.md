1.继承IComparer<T>接口用于提供两对象比较的方法
    public interface IComparer<in T>
    {
        int Compare(T x, T y);
    }
    返回负值（如 -1）表示 x 小于 y（即 x 在前）。
    返回正值（如 1）表示 x 大于 y（即 y 在前）。
    返回 0 表示 x 等于 y。
ps:不可用 lambda表达式或者匿名函数去填写函数中的 IComparer<T>参数

2.内置实现好了的比较器 CompareTo 

3.Comparison<T> 委托。返回值的含义与 CompareTo 相同
    定义为 public delegate int Comparison<in T>(T x, T y);
    可以使用Lambda表达式或者匿名函数去填写函数中的Comparison<T> 委托参数

4.集合排序的3个方式
    1）Sort + 比较器
        class AgeComparer : IComparer<Person>{
            public int Compare(Person x, Person y)
            {
            // 比较年龄
            return x.Age.CompareTo(y.Age);
            }
        }
        people.Sort(new AgeComparer()); 
    2）Sort + Comparison<T> 委托
        people.Sort((x, y) => x.Age.CompareTo(y.Age));
    3）Linq 的OrderBy
        var sortedPeople = people.OrderBy(p => p.Age).ToList();