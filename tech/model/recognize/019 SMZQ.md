![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo0hZehkdNdISd69qmmnO1H298lnQCBmu9Kn0KZUhOsHEzoVXNrKnJooVzuuUiaEMicRTnzGmNv2tic0Q/0?wx_fmt=jpeg)

#  如何用生命周期模型理解客户？

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。  **
![](https://mmbiz.qpic.cn/mmbiz_png/b96CibCt70iaajvl7fD4ZCicMcjhXMp1v6UQQ68afWhJytuHspOcDRtNqnosZfRiaqD9E6ZQs5jaeMyw9vTrDd3DTA/640?wx_fmt=png)
点击上方...设为星标  ‍  **

客户作为一个有生命的个体，有哪些特点？

今天介绍的第 **019** 号分析思维模型： **客户生命周期模型** ，能帮我们更好地理解客户，从而有利于营销活动的策划和运营管理的决策。

**1\. 模型介绍**

每个生命，都有一个从出生到死亡的过程。

客户生命周期，是指客户从第一次购买到最后一次购买间隔的时间。

结合以前介绍过的 [ RFM 分析模型
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&scene=21#wechat_redirect
"RFM 分析模型") ，我们可以把客户生命周期分成不同的阶段。

因为行业和品类的特殊性，划分阶段的标准不是唯一的。你可以根据自己的实际情况，定义适合自己业务的标准。

为了方便理解，下面介绍一种划分方法，供你参考。

**（1）新生客户（R < 360，F < 4） **

其中 R 代表最近购买日期与指定日期的间隔天数，F 代表累计购买次数。

如果客户最近购买次数不多，例如 360 天内购买不超过 4 次，那么我们定义为新生客户。

**（2）有效客户（R < 360，4 ≤ F < 7） **

如果客户最近购买次数较多，例如 360 天内购买了 4 到 6 次，那么我们定义为有效客户。

**（3）活跃客户（R < 360，7 ≤ F < 10） **

如果客户最近购买了很多次，例如 360 天内购买了 7 到 9 次，那么我们定义为活跃客户。

**（4）忠诚客户（R < 360，F ≥ 10） **

如果客户最近购买次数非常多，例如 360 天内购买了 10 次或 10 次以上，那么我们定义为忠诚客户。

**（5）休眠客户（360 ≤ R < 720） **

如果客户很久没有来购买，例如在最近 360 天到 720 天内没有再购买，那么我们定义为休眠客户。

**（6）流失客户（R ≥ 720 ）**

如果客户已经离开非常久，例如超过 720 天都没有再购买，那么我们定义为流失客户。

事实上，客户生命周期通常不是理想化的按顺序进行演变。

比如说，很多客户购买一次之后，就直接进入休眠甚至流失状态。

**2\. 应用举例**

我们以 Tableau 自带的超市数据集为例，对客户生命周期进行数据可视化的分析。

**（1）打开数据源**

首先，用 Tableau 打开软件自带的【示例 - 超市】数据。

**（2）创建计算字段**

其次，创建几个相关的计算字段。

【R 间隔天数】

{  FIXED  [客户名称]  :  
DATEDIFF  (  'day'  ,  MAX  (  [订单日期]  ),  DATE  (  "2021-12-31  "))}

【F 累计购买次数】

{  FIXED  [客户名称]  :  COUNTD  (  [订单 Id]  )}

【L 生命周期】

{  FIXED  [客户名称]  :  
DATEDIFF  (  'day'  ,  MIN  (  [订单日期]  ),  MAX  (  [订单日期]  ))}

【C 客户分类】

IF  [R 间隔天数]  >= 720 THEN  '6流失客户'  
ELSEIF  [R 间隔天数]  >= 360 THEN  '5休眠客户'  
ELSEIF  [F 累计购买次数]  < 4 THEN  '1新生客户'  
ELSEIF  [F 累计购买次数]  < 7 THEN  '2有效客户'  
ELSEIF  [F 累计购买次数]  < 10 THEN  '3活跃客户'  
ELSE  '4忠诚客户'  END

为了简化判断条件，上面对生命周期的阶段顺序做了适当的调整。

**（3）绘制分析图表**

最后，在 Tableau 中通过拖拽和点击的方式，生成分析的图表，包括以下几个小的步骤：

a. 把【F 累计购买次数】拖至【行】，把【R 间隔天数】拖至【列】。

b. 把【客户名称】拖至【标记】的【详细信息】，把【C 客户分类】拖至【颜色】。

c. 把【L 生命周期】拖至【大小】，把图例拖到左边，以节约显示的空间，并在工具栏选择【整个视图】，稍微调整一下客户分类的颜色，得到结果如下。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0hZehkdNdISd69qmmnO1H2icZRic6VKKoFrrVJaZJQ7oHYDLVzlcLBa4XiaelD5gjribKiaibZJvnEIh6A/640?wx_fmt=png)

从上图数据来看，忠诚客户的生命周期较长，流失客户的生命周期较短。  

从下图也可以直观看出，忠诚客户比流失客户的生命周期明显长很多。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo1XJM8hcfPXibbr3lzmXqctoheN68Gxfl4fxjdMZ39WG7ib01CricO28ypLJDGPdHQC7vt0WNyeDA5Jw/640?wx_fmt=png)

客户生命周期是动态的，你可以在任意时间点进行计算。  

单独的一个数据没有什么意义，只有经过对比，才能知道数据代表的真实含义。

比如说，客户平均生命周期 823 天，与过去相比是否有进步？与同行相比是否更好？

**最后的话**

客户作为一个人，往往都具有多面性。

理解客户，本质就是要洞察和满足客户的需求。

如果按照客户生命周期来划分客户，那么有助于我们理解不同阶段的客户需求，从而有针对性地采取运营策略，在成本可控的前提下，尽可能延长客户的生命周期。

![](https://mmbiz.qpic.cn/mmbiz_gif/n0NOdjkypXiccrnz7SvRYPwwblnYyZU2xHfzEt8V1LXPK6ibrQ9BaQ2YH7ZFx3CbYkgXbZeuPUc6PNrA57Fu2y8Q/640?wx_fmt=gif)

[ 福格行为
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477258&idx=1&sn=b55e3f648f903eec82177e78494e1f5f&scene=21#wechat_redirect
"福格行为") [ 杜邦分析
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477282&idx=1&sn=3507ad55727800c2c0a2089665a61634&scene=21#wechat_redirect
"杜邦分析") [ 矩阵分析
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477299&idx=1&sn=cdb2c2f2f7ac510f8de918f7dfca7b8c&scene=21#wechat_redirect
"矩阵分析") [ 夏普利值
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477319&idx=1&sn=a5e8945da69db7cd14e76173694fbc73&scene=21#wechat_redirect
"夏普利值") [ RFM分析
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&scene=21#wechat_redirect
"RFM分析")

[ 销售漏斗
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477417&idx=1&sn=f12ee0f36a8b459060dcb517088b22d8&scene=21#wechat_redirect
"销售漏斗") [ 正态分布
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477503&idx=1&sn=49d9b1e1355358a85a3ae15198ff2757&scene=21#wechat_redirect
"正态分布") [ 幂律分布
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477556&idx=1&sn=d2642afe4a49f020d73cc73b07b075a1&scene=21#wechat_redirect
"幂律分布") [ A/B 测试
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477755&idx=1&sn=6097fc38a9d2aa0562d0aaca39cb9222&scene=21#wechat_redirect
"A/B 测试") [ 线性回归
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477762&idx=1&sn=bfc400a41d0f344016de3529de612fef&scene=21#wechat_redirect
"线性回归")

[ 相关分析
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477819&idx=1&sn=b8aabdb1e2511fe5829bb75880036be4&scene=21#wechat_redirect
"相关分析") [ 聚类分析
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477838&idx=1&sn=4064489391aeaef9de2c3b69af564e68&scene=21#wechat_redirect
"聚类分析") [ 帕累托
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477874&idx=1&sn=cffe7167aa2a92a46a3fb26147cb5bde&scene=21#wechat_redirect
"帕累托") [ 本福特
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478148&idx=1&sn=a4d7a79a41b239afb126f1373015205f&scene=21#wechat_redirect
"本福特") [ 决策树
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478210&idx=1&sn=5024df4a09dd12c817f68c3bde37277b&scene=21#wechat_redirect
"决策树")

[ 同期群
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478233&idx=1&sn=5d304747a17105f0827a727b268d3289&scene=21#wechat_redirect
"同期群") [ 假设检验
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478244&idx=1&sn=691c8217e968c942e8a9a3ea4e5ad730&scene=21#wechat_redirect
"假设检验") [ Kano模型
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478304&idx=1&sn=45e14663d032ae66f270feb3ba05efc8&scene=21#wechat_redirect
"Kano模型")

![](https://mmbiz.qpic.cn/mmbiz_png/iaOib7ro3AqzmN91fpfXS59xeURluqkMibVtr0e3xHBVBO500PJCI3ZftE81I2WiaClictvjqLE91j0mkUibSBXr1yug/640?wx_fmt=png)

点击左下角的  阅读原文  可加入  我的 **免费** 知识星球  。  
如果对你有启发，麻烦你  点赞  支持一下  ，  谢谢！

#  ** ☟分享  ** ☟收藏  ** ** ** ** ❤  ** ** ** ** ** ☟  ** ** 点赞 ☟  ** ** 在看  **

预览时标签不可点

微信扫一扫  
关注该公众号



轻触阅读原文

![](http://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3rBmMJ1emiaHxRCj3Om1wuZZCsgHvFSR3sVQrPsicIlRiaGUicJD8KCZibrmu0FzGBc6aBzfBz3HLIeDA/0?wx_fmt=png)

林骥







****



****



  收藏

