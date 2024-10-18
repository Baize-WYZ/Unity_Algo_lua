 ```
 string message = state switch
    {
        "Start" => "Game is starting!",
        "Pause" => "Game is paused.",
        "End" => "Game has ended.",
        _ => "Unknown state." // 
    };
```

根据 state 获得相应的 string ，state 没有匹配的值，默认返回 “Unknown state.”


多条件组合
```
public string DetermineAction(int health, int stamina)
{
    return (health, stamina) switch
    {
        ( > 70, > 50) => "Attack",
        ( > 30, <= 50) => "Defend",
        ( <= 30, _) => "Retreat",
        _ => "Idle"
    };
}
```

结构体匹配
```
public string DescribeShape(object shape)
{
    return shape switch
    {
        Circle c => $"Circle with radius {c.Radius}",
        Rectangle r => $"Rectangle {r.Width} x {r.Height}",
        Triangle t => $"Triangle with base {t.Base} and height {t.Height}",
        _ => "Unknown Shape"
    };
}
```

类型匹配
```
public string ProcessInput(object input)
{
    return input switch
    {
        int i when i > 0 => "Positive Integer",
        int i when i < 0 => "Negative Integer",
        string s => $"String with length {s.Length}",
        null => "No Input",
        _ => "Unknown Type"
    };
}
```