# unity uGui 入门与催命 APP1

看一下今天能不能极限赶一个凑合用的极简版催命 APP 出来。UI 教程打算还看 Pathway 的。  
已装好安卓开发环境和 unity remote，嗨呀我这个东学一锄头西学一榔头的吃饭的桶。

## UI 入门

uGUI 是常用 UI 系统，IMGU（Immediate Mode GUI）是面向程序自制 unity 调试工具的。UI toolkit 是前两者结合的新系统但是还在开发中。  
先学 uGUI

### Canvas

- 锚点：锚点与组件距离不变，用于自适应。选中组件后摁 T 可视化锚点
- 按钮：按钮

  - color tint 改悬停（highlight）、点击（selected）颜色（都是正片叠底）

### 弱智问题速查

- 连手机要开 USB 调试模式，先开开发者模式然后在设置里搜 usb。之前 flutter 真机测试找不着可能也是这个问题卧槽 flutter 说的是选择 usb 的文件传输就没问题啊
- 连手机的 USB 测试不代表手机上的最终品质，会压缩字体，build run 代表最终品质

- 尽可能在字段声明时初始化引用对象，除非该字段依赖外部数据或构造条件。

- Instantiate 返回的是整个 GameObject（比如一个 Button），而不是直接返回 DateCell 脚本。

- scroll view 里是把 element 的 panel 放在 content 里面不是给 content 加 grid 然后放 element 进去

---

干起活来发狠了忘情了忘了记东西了。
但是总之搞完了 model，ui 呃，搞了一个界面但是丑到让我怀疑自己根本没学过美术。死去的单例模式又开始攻击我。  
今日成果：UI 零基础-》![](./截图/屏幕截图%202025-07-09%20233537.png)+models  
另外 Pathways 的 ui 教程主要针对电脑游戏，不深入且偏离我的目的了，又在别处摸索了不少教程
https://youtu.be/Unnd0cOSiLU?si=wCWUuQ7hOdlU4NSG
