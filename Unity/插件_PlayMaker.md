FSM 有限状态机

状态切换通过transition（实质上是一个事件）  PlayMaker中有两种 一种为全局 一种为局部。当全局事件发生就会调用该transition 而局部需要处于transition的前一状态。全局transition可以让状态机更加整洁
![alt text](image.png)

