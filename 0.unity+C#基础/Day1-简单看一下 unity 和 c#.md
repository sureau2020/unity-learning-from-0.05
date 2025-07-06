# 简单看一下 unity 和 c#

今天看一下 unity3D 基础操作 && c#基础语法

## unity3D 入门

使用 unity 官方 Pathway 教程，从 Unity Essentials 开始。好用啊好用啊，这种基于文本但也有步骤视频演示的教程看起来好爽好简单。  
放一个 pathway 链接在这里：https://learn.unity.com/pathways  
PS 有时候真把用户当小孩哄，感觉比那个 scratch 更适合推荐给小学生家长起码孩子真能学到点什么

### 视图操作备忘录

有 blender 基础所以视图还挺好上手，只记几个快捷键（？）

- 在 Hierarchy 窗口中，双击物体名称以在 3D 视图中框选
- 在 3D 视图中选择物体 ，按 F 键也将其框选
- 框选后按住 Alt，按住鼠标左键来环绕物体
- 按住鼠标右键并使用 WASD 键在空间中移动来激活飞越模式
- 左上角可切换 world 和 local 坐标系，world 坐标系永远不变
- 恢复默认的自由视图，只需右键单击右上角场景坐标轴，然后选择 free
- View: Q 键盘第一行按键从左到右 👇
- Move: W
- Rotate: E
- Scale: R
- Rect: T
- 选择 Camera，按 Ctrl+Shift+F 将相机与当前视图对齐

---

不是快捷键但值得一记的东西

- 默认情况下， 游戏视图会显示 “层级” 窗口中第一个活动的摄像机
- 1 个单位通常等于 1 米
- 有了 Rigidbody 组件，球就会拥有质量并受到重力的影响
- (Mesh Filter) 组件决定了游戏对象 (GameObject) 的形状。网格是一个线框 3D 模型。对于球体来说，网格被设置为球体 (Sphere) 形状
- Mesh Renderer 组件控制球的外观。尝试找到你应用到球上的材质。当你应用材质时，它会显示在这个组件中
- 球体碰撞器 (Sphere Collider) 组件定义了游戏对象的物理边界，用于碰撞。尝试找到你创建并应用的物理材质 (Physic Material)
- Mesh collider 组件中，启用 Convex 属性为不规则物体添加碰撞
- 当您将 GameObject 从 Hierarchy 窗口拖到 Project 窗口中的任何文件夹中时 ，它会将该对象转换为预制件
- 层次结构窗口中的块变为蓝色，表示它是预制件的副本或实例
- 双击 Block 预制件进入预制件编辑模式
- 右键单击 ​​ 选定的块创建空父级
- 主摄像机带音频监听器，不允许在一个场景中拥有多个活动的音频监听器
- 每个 Audio Source 播放一个音频片段
- Audio Source 组件中，找到 Spatial Blend 属性并将滑块从 0 （完全 2D）拖动到 1 （完全 3D）
- component: Play Sound at Random Intervals
- Collider 组件的 Is Trigger 取消物理碰撞但检测碰撞
- 至少其中一个对象附加了 Rigidbody 组件时，才会调用 OnTriggerEnter 函数

## 针对 unity 的 C# 入门

主要记录和 JAVA 不一样的地方和我记得模糊的地方

### 特性

- C# 编写的脚本是可编辑的组件
- public 在 editor 的 Inspector 中公开变量
-

### 语法

- public class Collectible : MonoBehaviour //继承自 MonoBehaviour（a required class for all GameObjects in Unity）
- transform.Rotate(0, 1, 0);//xyz 旋转一度
- 在数字末尾加上“f”来明确表明它是浮点数
- gameObject 指自己
- Instantiate(谁, position, rotation);//实例化
- other.CompareTag("Player")// other 是玩家不
- bool  
  网上找了个针对 java 开发者的[cheat sheet](./Cheat%20Sheet.pdf)  
  看了一下有点像 java 混了点 c++，具体语言特性明天再看吧

### 代码规范

- script 名字、method 名字 PascalCase
- var 名字 camelCase

---

今天先这样吧，完成了 unity3D 的入门，简单看了一下编程部分  
明天搞 2D 入门、尝试打包、shader graph 入门  
另外 unity2022 版本的打包教程是坏的，明天可能跟着 6.0 摸索打包
