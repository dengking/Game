# MonoBehaviour 



## CSDN [Unity 脚本基类 MonoBehaviour 与 GameObject 的关系](https://blog.csdn.net/hihozoo/article/details/66970467)

### 四、脚本与GameObject的关系

被显式添加到 Hierarchy 中的 `GameObject` 会被最先实例化，`GameObject` 被实例化的顺序是从下往上。`GameObject` 被实例化的同时，加载其组件 component 并实例化，如果挂载了脚本组件，则实例化脚本组件时，将调用脚本的 Awake 方法，组件的实例化顺序是也是从下往上。在所有显式的 `GameObject` 及其组件被实例化完成之前，游戏不会开始播放帧。

> NOTE: 关于 Hierarchy ，参见 docs.unity3d [The Hierarchy window](https://docs.unity3d.com/Manual/Hierarchy.html)

当 `GameObject` 实例化工作完成之后，将开始播放游戏帧。每个脚本的第一帧都是调用 Start 方法，其后每一帧调用 Update，而且每个脚本在每一帧中的调用顺序是从下往上。

总结：被挂载到 `GameObject` 下面的脚本会被实例化成 `GameObject` 的一个成员。
