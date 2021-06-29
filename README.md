# document
document
- 组件化 <br>
  * 组件化需要解决两个问题，业务模块的划分以及组件间的通信。业务模块的划分是比较麻烦的，因为之前写的都耦合在了一起，目前我们也只有一个发票的模块独立拆分了出来。组件间的通信可以采用 ARouter。ARouter 的源码我倒是没有看过，不过之前也写过路由跳转，核心的思想就是生成一个 Map，Path 对 Activity 的映射。实现方式有两种，第一种是通过元数据的形式，即在 Manifest 注册 Activity 时添加 meta-data 信息，然后在 Application 的 onCreate 时去扫描所有的 Activity 生成 Map，这种方式实现简单，几十行代码就能写完了。第二种方式则是比较传统的通过编译时注解 + JavaPoet 的形式，和 ButterKnife 原理一样。但是写的时候还是发现一些问题的，注解处理器在每个模块下都要引入，生成的类的全限定名是当前的包名 + 类名，里面就一个 public static 的方法，方法里面就是写好的 HashMap 一系列的 put 方法，接下来就是要每个模块生成的 Map 进行合成即可，但是问题来了，在 app 模块是不知道其他模块的名字呀，于是只能在 assets 目录下配一个 json 文件用来读取每个模块的模块名，有了模块名就有了前面生成的类的全限定名了，然后反射执行方法合成 Map 即可。
  * [Android组件化，全面掌握！](https://juejin.cn/post/6881116198889586701)
- Android 进阶篇---＞ App运行时大图监控
  * [Android 进阶篇---＞ App运行时大图监控](https://blog.csdn.net/qq_42795723/article/details/107822387)
  * [一起玩转Android项目中的字节码](http://quinnchen.cn/2018/09/13/2018-09-13-asm-transform/)
  * [Fresco图片显示原理浅析](https://www.jianshu.com/p/2bb77edb3011)
- JVM基础 -- 字节码
   * [JVM基础 -- 字节码](http://zhongmingmao.me/2019/01/03/jvm-basic-bytecode/)
   * [Jvm系列3—字节码指令](http://gityuan.com/2015/10/24/jvm-bytecode-grammar/)
   * [深入理解JVM - 虚拟机字节码指令集](https://blog.csdn.net/xiaolyuh123/article/details/104030176)
   * [轻松看懂Java字节码](https://mp.weixin.qq.com/s/HMuARN4dGSJtPTV8fZDW5Q)
 - [今日头条屏幕适配方案终极版正式发布!](https://juejin.cn/post/6844903697000972295)