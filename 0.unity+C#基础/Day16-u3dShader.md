# u3d+shader 入门精要

今天 u3d 收尾，下午看 shader 吧

## u3d

### 杂记

- [SerializeField]private int a;在 editor 里能调用修改但其他 class 调不了
- readonly int a=1;实例化一个物体时可以赋值，之后不再变化
- FixedUpdate()物理运算，与物理引擎绑定，不受帧率波动影响
- 不要在 FixedUpdate() 里检测用户输入，因为 FixedUpdate() 频率可能跟不上帧率，可能漏掉一些键盘事件。
- LateUpdate()给相机
- Awake(){}可替换 start()仅当物体被唤醒时调用
- Object Pooling 对象池（创建好然后只是 active 或不 active）以避免频繁创建和删除物体
- 实体组件系统 Entity Component System (ECS) 是新面向数据技术堆栈 Data-Oriented Technology Stack (DOTS) 的一部分
- array 定长，list 动态
- 由于硬币是一个触发器，不会对物理做出反应，因此 OnTriggerEnter 会检测玩家和硬币之间的第一次碰撞。
- DontDestroyOnLoad(gameObject);防止加载别的场景物体被摧毁
- static 变量属于类本身，不依赖于某个对象实例。即使重新加载场景，变量的值也会被保留在内存中。
- 单利：

```
public class GameManager : MonoBehaviour
{
   void Awake()
   {
      if (Instance == null)
      {
         Instance = this;
         DontDestroyOnLoad(gameObject);
      }
      else
      {
         Destroy(gameObject);
      }
   }

   public static GameManager Instance { get; private set; }

}
```

- checkout a branch 你的 工作目录（working directory） 会被更新为该分支对应的文件和状态。表示你“切换到某个分支”
- clone, branch, checkout, add, commit, push
- Window > Analysis > Profiler.
- 1000 ms / target frames per second = ms budget 为了达到 60 FPS 的目标，每帧的毫秒预算为 16
- profiler 换层级看自己定的 sample

```
Profiler.BeginSample("Moving"); // begin profiling

Move();

Profiler.EndSample(); // end profiling
```

- C#（Unity 使用的语言）只支持单继承，也就是说一个类只能继承自一个父类。（注意：可以实现多个接口，但类只能继承一个。）
- public int Score { get; set; }方法语法糖可改：

```
public int Score
{
    get { return score; }
    set {
        if (value >= 0) score = value;   // 防止负分
    }
}
```

- 自定义脚本的运行逻辑（比如 Update()、FixedUpdate()、LateUpdate() 等）都是在 PlayerLoop 阶段执行的
- 在 C# 中，Extension Method（扩展方法） 是一种特殊的静态方法，它让你像调用实例方法一样给现有的类添加新功能，而无需修改原来的类或继承它。
- Extension Method（扩展方法） 是一种特殊的静态方法，它让你像调用实例方法一样给现有的类添加新功能，而无需修改原来的类或继承它。你想给 string 类型加一个新功能：比如统计字符串中的单词数。

```
public static class StringExtensions
{
    public static int WordCount(this string str)
    {
        return str.Split(new[] { ' ', '\t', '\n' }, StringSplitOptions.RemoveEmptyEntries).Length;
    }
}

```

---

下午出去了，shader 明天再看吧  
目前是第 16 天、更可能是第 17 天。以下是目前学习的总结：  
unity 引擎方面，学完了 unity 各系统基础操作，了解了 unity 推荐的组件通信方法、游戏结构、协程相关概念。在教程外额外制作了两个原型，一个是包含日历系统、数据持久化、系统通知的类 todo app，一个是仿接名字小游戏的简单 webGL 游戏。  
shader 方面理解了渲染流水线。学习并使用 shader graph 制作了卡渲 shader，又跟着教程在 built-in pipeline 写了 shaderLab 完成了第一个卡渲 shader。  
接下来的学习重点是 unity shader 入门精要，开始学习书里那堆数学；再之后可以考虑 Games101 或者英文资源（？）。同时 unity 引擎方面继续深入研究 animation 系统和后期处理（？）。C#方面看多线程。网络联机的优先级不高，好像还要学 lua 啥的，但有时间的话也看一眼。  
目前感觉可以开始人生养成 app 的制作了，目前可见卡点有三个：1 美术素材（慢慢画吧）、2unity 后台运行相关方案、3 风格化渲染的 3D 背景（这个好像可以最后加，边做边看）  
另外在 Unity 之外，还在上学校的网课嘛，所以这些天也看了一些话剧剧本：日出、打出幽灵塔、玩偶之家、关汉卿、茶馆、终身大事。这个老师我上周还夸过她讲剧本讲历史不讲政治，这周上课就涉政，，，，，算了谁能对北美院校的亚洲研究部门抱有任何期待，，，，，，上完课赶紧跑了。  
在这之外刷完了 gbc，mygo 看了两集，不知道啥时候有时间继续看。我感觉比起 gbc 我更喜欢 mygo 一些。
我感觉现在的时间还没有利用充分，虽然精力有限但是现在的时间分配还不是太合理，主要是刷手机时忘了我还有动画片要看。
