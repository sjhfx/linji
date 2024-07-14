![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo3CS9iaUGdQRibMviblGQ4NGswgIfKqSuQtr0xwCxYZy5uLngx3SZbKUHl3312Sl80icUdCCV2y2DibjHg/0?wx_fmt=jpeg)

#  如何用标杆分析模型获得提升？

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。  ** ** ▲  ** 点击上方卡片...设为星标，用数据化解难题  **

你有没有向标杆学习的经历？

你知道如何学习才能更加高效吗？

你曾经从标杆身上学到了什么？

今天介绍的第 **020** 号分析思维模型： **标杆分析模型** ，能帮我们正确地向标杆学习，从而更快地获得提升。

**1\. 模型介绍**

标杆分析模型，是指与标杆进行对比，  分析标杆的优点，并  找到适合自己的  行  动  方法。

无论是个人，还是企业，甚至是国家，都可以运用标杆分析模型，经过分析、对比和改进，形成良性循环。

对个人来讲，为了提升自己的能力，可以找几个自己最佩服的人，把他们作为标杆，分析他们身上值得学习的地方，通过对比，找到自己可以改进的方向，确定下一步行动的方案。

很多家长喜欢说：你看看别人家的孩子……再看看你……

家长其实是在帮孩子树立标杆，但是大多数孩子都有抵触内心。

其实家长不妨从自身出发，看看别人家的家长，再看看自己，经过分析之后，试着去努力改变自己，或许孩子的问题也就解决了。

孟子在两千多年以前说过一句话：

> 行有不得者，皆反求诸己。

我觉得这句话说得非常好，适用于每一个人，每一家企业，甚至每一个国家。

我们自己应该向标杆好好学习，如果行动没有达到预期的效果，也要从自己身上找原因，而不要去怪罪他人。

对企业而言，为了提升公司的业绩，可以找几家标杆企业，分析总结标杆企业的产品设计、销售、服务、经营策略等等，找到可以改进的方法，从而做出更加科学的决策。

**2\. 应用举例**

下面以 Tableau 自带的超市数据集为例，假设要按地区来进行标杆分析，对比各地区与标杆地区的销售额差异是多少？

你可以参考下面的方法和步骤，举一反三，应用到其他类似的标杆分析中去。

**（1）打开数据源**

首先，用 Tableau 打开软件自带的【示例 - 超市】数据。

**（2）创建参数**

点击数据旁边的三角形，选择【创建参数】：

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3CS9iaUGdQRibMviblGQ4NGswp6W0gm4ibWnDPPvJYfib5Z0AbgmX6t2a3YdSoFCudLggfL4icd5HrS4icg/640?wx_fmt=png)

参数【名称】后面填写【  标杆地区
】，【数据类型】后面选择【字符串】，【允许的值】后面选择【列表】，【通过以下各项添加值】后面选择【地区】，点击【确定】按钮。  

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3CS9iaUGdQRibMviblGQ4NGswEsKAezEqAtcI96J2vQHHWpibziaWjwLNwn1mBics5lSlqiclQURSHMLl7A/640?wx_fmt=png)

**（3）创建计算字段**  

其次，创建两个相关的计算字段。

【标杆销售额】

IIF  (  [地区]  =  [标杆地区]  ,  [销售额]  , 0)

【对标差异】

SUM  (  [销售额]  )-  SUM  ({  EXCLUDE  [地区]  :  SUM  (  [标杆销售额]  )})

其中 EXCLUDE 是 Tableau 的一种 LOD 表达式，表示如果指定的 [地区] 维度出现在视图中，那么在计算 SUM([标杆销售额])
时，会排除这个维度，相当于往上跳了一层，获得更高层级的计算结果。

所以，用该地区的销售额，减去这个表达式，就得到该地区与标杆地区之间的销售额差异，我们简称为【对标差异】。

**（3）绘制分析图表**

最后，在 Tableau 中通过拖拽和点击的方式，生成分析的图表，包括以下几个小的步骤：

a. 把【对标差异】和【销售额】分别拖至【列】，把【地区】拖至【行】。

b. 把【对标差异】拖至【标记】的【颜色】，双击【标记】下方的空白区域，输入 [地区]=[标杆地区] ，并把标记类型修改为【颜色】。

c. 新建一个仪表板，把前面做好的图表拖进去，然后设置标题、颜色、边框、图例、下拉列表等细节，得到结果如下：

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3CS9iaUGdQRibMviblGQ4NGswcOrXHsWYS4ynBfIzJKGu5e3l1ESLxv6MoljOpPoNPE4WicwRRRTVm1A/640?wx_fmt=png)

**注意，标杆的选择非常重要！如果选错了标杆，后果会很严重。**  

比如说，如果企业把销售业绩最差的西北地区作为标杆，那么业绩将很难获得提升。

同理，我们在选择偶像的时候也要特别注意，要多学习偶像身上的优点，而不是缺点，比如吸毒、赌博等恶习，可千万不要学。

**最后的话**

有人说，榜样的力量是无穷的。

**与自己反复试错相比，向标杆学习肯定会更加高效。**

如果你能合理运用标杆分析模型，充分发挥自身的优势，那么可能起到事半功倍的效果，因为标杆不仅确立了标准、树立了榜样，而且提供了一套切实可行、行之有效的经验。

写到这里，100 种分析思维模型的 20% 就更新完成了。

接下来，按照二八法则，我计划把重心转向分析思维模型的应用，写作更加通俗易懂的文章，希望能够帮助更多人用数据化解难题。

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
"Kano模型") [ 生命周期
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653478327&idx=1&sn=4bd1bb87e2d06bf6089fb29ce6b80b8e&scene=21#wechat_redirect
"生命周期")

![](https://mmbiz.qpic.cn/mmbiz_png/iaOib7ro3AqzmN91fpfXS59xeURluqkMibVtr0e3xHBVBO500PJCI3ZftE81I2WiaClictvjqLE91j0mkUibSBXr1yug/640?wx_fmt=png)

预览时标签不可点

微信扫一扫  
关注该公众号



轻触阅读原文

![](http://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3rBmMJ1emiaHxRCj3Om1wuZZCsgHvFSR3sVQrPsicIlRiaGUicJD8KCZibrmu0FzGBc6aBzfBz3HLIeDA/0?wx_fmt=png)

林骥







****



****



  收藏

