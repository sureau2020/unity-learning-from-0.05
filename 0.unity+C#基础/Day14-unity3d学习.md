# U3D 学习

## U3d 杂记

- playerRb = GetComponent<Rigidbody>(); AddForce method 跳跃，ForceMode.Impulse
- Physics.gravity \*= 调世界 gravity
- OnCollisionEnter(Collision collision)自带函数
- 利用捆绑 box collider 来获取图像中点坐标
- 两倍大的背景在中点回到原点开始重复
- script 间通信：1declare private ScriptClassName playerControllerScript;2start 里靠 GameObject.find("Player"//tag).GetComponent<ScriptClassName>()建立链接;3.可以调了但只能调 public 的
- animator 状态机，箭头看条件，parameter 调状态
- animator 作为 script 一个变量，playerAnim.SetTrigger(“Jump_trig”);切换动画
- public ParticleSystem explosionParticle 控粒子，.Play()开始动画
- BGM 绑相机上
- public AudioClip 拖音频素材，谁响在谁身上，private AudioSource 播放 AudioClip
- 让相机成为空物体的子物体，script 控制子物体旋转从而让相机旋转
- 空物体当 var，player 用空物体.transform.forward
- (player.transform.position - transform.position).normalized;算方向
- update 外协程 Coroutine，1 调用 StartCoroutine(DoSomething());2 IEnumerator DoSomething()
  {
  yield return new WaitForSeconds(2f); // 等两秒
  Debug.Log("OK");
  } 会等两秒然后出 OK，“能中途暂停一下再继续执行”的函数。

  ```
    IEnumerator Coroutine() {
        // 执行一部分
        yield return 等一下
        // 过一会再回来继续
    }
  ```
- rb.AddTorque加扭矩
-
