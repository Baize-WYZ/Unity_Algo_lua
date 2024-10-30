# PlayerPrefs
```
https://docs.unity3d.com/cn/2021.2/ScriptReference/PlayerPrefs.html
```
用于存储string、 float、 integer 到用户平台的注册表中 数据存储位置依赖于使用的操作系统

## 删除值
```
 PlayerPrefs.DeleteAll()
 public static void DeleteKey (string key);  有就删除没有就无效
```

## 设、取值（int\string同理）

```
 public static float GetFloat (string key);
 public static float GetFloat (string key, float defaultValue); 不存在key则返回 defaultValue

 public static void SetFloat (string key, float value);
```

## 检测是否有偏好值

```
public static bool HasKey (string key);
```

## 保存所有偏好到磁盘
 默认情况下，Unity 会在 OnApplicationQuit() 执行过程中将偏好写入磁盘。
```
public static void Save ();
```


# lua中调用
需要架构支持
```
CS.UnityEngine.PlayerPrefs.HasKey('language')
```


