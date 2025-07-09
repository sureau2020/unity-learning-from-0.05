# INTRO TO UNITY SHADER CODING

对不起，上午又搞同人去了。  
打算明天或者后天赶紧把之前的催命 APP 做出来，之前用着感觉效率提升了不少，但当时有内存泄露的毛病就没再用，这次用 unity2D 敲一个出来当练习了。  
今天先啃这个吧：https://roystan.net/articles/toon-shader/  
（学到一半我才发现这是一个 built-in pipeline 的教程，现在基本鼓励用 URP 了，不知道该去哪里找入门教程，我学完他这个看看）  
如果啃完了还不知道明天学啥就去做 APP，如果有啥特感兴趣想明天研究的那就后天再 APP。

## 资源链接

看教程时顺藤摸瓜找到好多资源，在这儿码一下

- 昨天 shader graph 的文档，有全 nodes 解释：https://docs.unity3d.com/Packages/com.unity.shadergraph@17.3/manual/index.html
- 用代码编写 shader 官方入门：https://docs.unity3d.com/Manual/SL-ShadingLanguage.html （这个好，我学学再回来啃 Roystan 老师的，路上看见啥链接还放在这个板块）
- https://www.shadertoy.com/ 一个 Shader 分享网站可以看别人的效果和代码
- https://positiveczp.github.io/%E7%BB%86%E8%AF%B4%E5%9B%BE%E5%BD%A2%E5%AD%A6%E6%B8%B2%E6%9F%93%E7%AE%A1%E7%BA%BF.pdf 别人推的
- Unity shader 入门精要，微信读书上可以读，看了两眼感觉挺好的我看看

## Writing custom shaders in URP

官方教程，URP 指通用渲染管线 https://docs.unity3d.com/Manual/urp/writing-custom-shaders-urp.html  
卧槽 unity 把人当 blender 耍啊这是哪门子文档这是一个个 node 啊，比 galgame 还有互动性

### ShaderLab（unity shader 配置语言）的基本结构

- Shader “Example/xxxxx” ：这个 shader 的名字和（在 shader 里的）位置
- Properties{}：暴露在外允许 material 修改的参数
- Tag{}: subshader tags，在何种情况下使用这个 shader，例如{"RenderType" = "Opaque" "RenderPipeline" = "UniversalPipeline"}，具体 tag 大全请看：https://docs.unity3d.com/Manual/SL-SubShaderTags.html
- Pass{}: 放 HLSL 代码的但也可以<optional: name>
  <optional: tags>
  <optional: commands> 具体看这个：https://docs.unity3d.com/Manual/SL-Pass.html

#### 值得记录的常用 PASS 中的 Tags：

- LightMode: 接受啥光照信息，教程中使用 ForwardBase(用于 Forward rendering ；应用环境光、主定向光、顶点/SH 光和 lightmaps 。是 BUILT-IN 管线。这个我得自己改改看有无 URP)

### HLSL 入门

- 包含一下标准库  
  `#include "Packages/com.unity.render-pipelines.universal/ShaderLibrary/Core.hlsl"`  
  标准库的文档在这里看：https://docs.unity3d.com/Manual/urp/use-built-in-shader-methods.html
- smoothstep(,,) takes in three values: a lower bound, an upper bound and a value expected to be between these two bounds

看到这里感觉了解了最基础的基础能看懂 R 老师的教程了所以回去看，有啥要点还会按照现有笔记结构补充

### 值得记录的理论

- smoothstep 非线性变化，当值从 0 到 0.5 时，它会加速；当值从 0.5 到 1 时，它会减速。这使得它非常适合平滑地混合值

- Blinn-Phong 光照模型中，specular reflection（高光） as the dot product between the normal of the surface and the half vector. The half vector is a vector between the viewing direction and the light source; we can obtain this by summing those two vectors and normalizing the result.

---

教程 belike![](./截图/屏幕截图%202025-07-08%20220239.png)

这个是 built-in，主要还得学 URP，不知道接下来学啥我检索检索  
检索结果加到资料里了，但明天还是打算去做 APP，没有催命 APP 感觉效率极其低下有点自我厌恶了。
