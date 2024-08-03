https://docs.unity3d.com/cn/2019.4/Manual/Packages.html

1.package如何起作用
    ![alt text](image.png)
    项目中与包相关的主要文件是 
        manifest.json 声明项目所需要的所有包和对应版本
        packages-lock.json  声明每个包的详细信息，以及每个包的依赖包和版本，还有来源（local 或者某url）。在发生包冲突的时候会优先选择锁定文件中的包。
            https://docs.unity3d.com/cn/2019.4/Manual/upm-manifestPrj.html
        
    包中主要文件是
        package.json 始终位于包的根目录，并且包含有关包的重要信息，例如其注册名称和版本号，定义了与用户通信的有用信息，例如出现在 UI 中的用户友好名称、包的简要说明以及该包兼容的最低 Unity 版本。
            https://docs.unity3d.com/cn/2019.4/Manual/upm-manifestPkg.html
        
2.脚本中与 Package Manager 进行交互
    PackageManager.Client 查找包、浏览包列表以及通过脚本安装和卸载包
    PackageManager.PackageInfo 包含包的状态，包括从包清单和注册表获取的元数据。

3.引用包资源
    "Packages/<package-name>/..." 例如"Packages/com.unity.images-library/Example/Images/image.png"
    相比之下，应使用以下方案访问项目资源
        "Assets/..."
4.AssetDatabase.LoadAssetAtPath (string assetPath, Type type);
    返回给定路径 **assetPath** 下 **type** 类型的第一个资源对象。
    **assetPath** 参数不区分大小写。
    Unity 中的**所有**资源名称和路径都使用正斜杠，即使是在 Windows 上。
    这将仅返回在 Project 视图中可见的资源对象。如果未找到资源，LoadAssetAtPath 返回 Null。
5.Path.GetFullPath(String path)
    返回path的绝对路径 在System.IO 命名空间下。
6.Package Manager 优先选择从其他来源安装的包（如嵌入式包和使用本地路径、Git URL 声明的依赖项和内置包）

