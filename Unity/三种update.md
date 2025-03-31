Update() vs LateUpdate() vs FixedUpdate() 对比
方法	触发时机	调用次数	主要用途
FixedUpdate()	物理更新前	可能一帧多次或不执行	物理计算（刚体、力学）
Update()	每帧一次	1 次/帧	普通逻辑（移动、输入检测）
LateUpdate()	Update() 之后	1 次/帧	依赖 Update() 的逻辑（摄像机跟随）
确保某个逻辑仅在 Update() 后执行一次，用 LateUpdate()；如果你是处理物理相关的逻辑，用 FixedUpdate()。

**Update和LateUpdate 都是在一帧执行一次 Update和LateUpdate主要是用于以来Update计算结果的变化。每帧的执行间隔与帧率相关，deltaTime可以拿到每帧间时间。FixedUpdate执行间隔依靠的不是deltaTime 而是Time.fixedDeltaTime，所以在一帧中可能会执行多次（fixedDeltaTime <  deltaTime）或者不执行（fixedDeltaTime >  deltaTime）或者执行一次（fixedDeltaTime ==  deltaTime）FixedUpdate主要执行物理相关，执行频度越高 带来的性能影响就越高**