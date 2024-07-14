![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo3IlicNZCaSAKyia7nlLkgE3L0PVsem5qXMX3v5QnPEKEBJBjkVFibCMWQqcClLg60KYRhL2rhbO4OhA/0?wx_fmt=jpeg)

#  100种分析思维模型（011号）

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。

上次介绍的  [ 线性回归模型
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477762&idx=1&sn=bfc400a41d0f344016de3529de612fef&scene=21#wechat_redirect)
，与下面将要介绍的模型有很大的关系，但是侧重点有所不同。

线性回归模型中的两个变量，分别称为自变量和应变量，它们之间有逻辑上的主次之分，侧重于分析自变量给应变量带来的影响。

比如说，广告费是自变量，商品销量是应变量，我们重点分析的是广告费能给商品销售带来多少增量，而不是反过来。

今天介绍的第 **011** 号分析思维模型： **相关分析模型** ，是寻找变量之间的「相互」关系，并没有主次之分，侧重于解释变量之间的关联。

**1\. 模型介绍**

相关分析，其实就是寻找变量之间相互关联的程度。

如果一个变量改变的时候，另一个变量也朝着相同的方向发生变化，那么我们就说这两个变量之间存在正相关性。

反之，我们就说这两个变量之间存在负相关性。

如果一个变量无论怎么改变，另一个变量都不会跟着变，那么我们就说这两个变量之间没有相关性。

比如说，个子高的人，通常体重会重一些，个子矮的人，通常体重也会轻一些，所以说身高和体重存在正相关性。

当然，也会有例外的情况，因为有些人是又高又廋，但总体而言，大多数人是符合相关规律的。

相关分析通常包括以下几个步骤：

**第一步，收集相关数据** 。

首先，收集相关数据，一般是成对出现的数据，从而为后面的相关分析做好准备。

**第二步，绘制散点图形。**

把一个变量作为横轴，另一个变量作为纵轴，画出散点图形，观察数据的分布，大致判断相关性。

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3ET7Ef1QqvYiaF9T08APF8yYL5baRxdBtZj9Y3w4NxH2Qy9kUXtqwz1vd2cOu6LAs6S1x8xYjCVmA/640?wx_fmt=jpeg)

一般情况下，我们所说的相关，都是指线性相关。

**第三步，计算相关系数。**

相关系数有两大特点：

（1）是介于 -1 到 1 之间的常数

相关系数等于 -1 表示完全负相关，等于 0 表示完全不相关，等于 1 表示完全正相关。

在实际应用中，我们通常把相关系数的取值，分成几个不同的区间，来表示不同的相关程度：

  * 0.0 ≤ |相关系数| < 0.3，表示不相关 
  * 0.3 ≤ |相关系数| < 0.5，表示弱相关 
  * 0.5 ≤ |相关系数| < 0.8，表示中度相关 
  * 0.8 ≤ |相关系数| < 1.0，表示强相关 

（2）它不受变量单位的限制

相关系数可以将单位不统一的数据，加工成一个简洁的描述性数据。

比如说，身高的单位是厘米，体重的单位是千克，我们也能计算出它们的相关系数。

需要注意的是，相关系数与显著性检验的 p 值不同，相关系数用来反映相关性的强弱，而 p 值用来检验是否存在相关关系，一般情况下，当 p 值小于 0.05
时，才可以判断存在相关关系。

**2\. 应用举例**

以 Tableau 自带的超市数据为例，我们应用相关分析模型，分析技术类产品的子类别之间是否有相关关系。

**第一步，收集相关数据** 。

（1）打开 Tableau Desktop 2021.1 版本，在已保存的数据源中，点击【示例 - 超市】。

（2）导航到【数据源】选项卡，把左边的【订单】表，拖动到右边的画布区域。

（3）编辑关系选择【订单 Id = 订单 Id（订单1）】，如下图所示：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3ET7Ef1QqvYiaF9T08APF8yCTPg1tPeLbp04Y0IXlmIWh8KquvNBVR0U3w2knGK3aLDGOO9k0C37w/640?wx_fmt=jpeg)  

** ‍‍‍‍‍‍‍‍‍  第二步，绘制散点图形。 **

（1）双击【工作表 1】，重命名为【散点图】。

（2）把【子类别】和【销售额】拖到【列】功能区。

（3）把【子类别（订单1）】和【销售额（订单1）】拖到【行】功能区。

（4）把【订单 Id】拖到【标记】卡的【详细信息】。

（5）把【类别】拖到【筛选器】功能区，选中【技术】后，点击【确定】。

（6）把【类别（订单1）】拖到【筛选器】功能区，选中【技术】后，点击【确定】。

（7）依次点击菜单：【分析(A)】→【趋势线(T)】→【显示趋势线(T)】。

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3ET7Ef1QqvYiaF9T08APF8y4lKTV7USfYT0wZJS9LNTGYbKEc6xXE4OQdoFqceVFbKnI4yibldgBjg/640?wx_fmt=jpeg)

把鼠标放在趋势线的上方，可以看到其中的 p 值都大于 0.05，基本可以判断不存在相关关系。

从散点图的分布中也可以看出，产品的子类别之间基本都没有相关性。

**第三步，计算相关系数。**

（1）复制【散点图】工作表，并重命名为【相关系数】。

（2）依次点击菜单：【分析(A)】→【创建计算字段(C)...】。

（3）将字段命名为【相关系数】，输入以下公式并点击【确定】：

    
    
    CORR( { INCLUDE [订单 Id] : SUM([销售额 (订单1)])},   
                { INCLUDE [订单 Id] : SUM([销售额])})  
    

（4）分别将【相关系数】拖到【标记】卡的【颜色】和【标签】。

（5）移除【列】中的【销售额】和【行】中的【销售额 (订单1)】。

（6）将【标记类型】改为【方形】，移除【标记】卡的【订单 Id】。

（7）编辑颜色，选择【绿色-蓝色-白色发散】，点击【确定】，调整字体大小之后，如下图所示：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3ET7Ef1QqvYiaF9T08APF8yMHjUvC4kKYNU3dRiaZZGJKYsGCVYqiaq7qCnDDoeAoibzIDqbvTWVIc8g/640?wx_fmt=jpeg)

从上面的相关系数矩阵中，可以看出，除了对角线相同子类别的相关系数为 1 以外，其他相关系数的绝对值都小于
0.3，事实上，其中相关系数的平方，就等于散点图趋势线中的 R 平方值。

综上进行业务判断，我们可以得出相关分析的结论：从订单层面的销售额指标来看，技术类产品的子类别之间没有相关性。

**最后的话**

即使两个变量之间有相关关系，也不代表其中一个变量的改变，是由另一个变量的变化引起的。

比如说，国家的诺贝尔奖数量，与巧克力消费量之间呈现正相关关系，但这并不是说，多吃巧克力有助于获得更多的诺贝尔奖。

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3ET7Ef1QqvYiaF9T08APF8yHFHCbUpkqibA34ra2Via2YbEeuFzhhVvbeOxibxCibC4nmnMlV0wkQVqBQ/640?wx_fmt=jpeg)

一种合理的解释是，诺贝尔奖的数量与巧克力的消费量，很可能都是由其他变量导致的，例如国民的受教育程度和富裕程度。

最后，请一定要牢牢记住， **相关关系不等于因果关系** 。  ****

![](https://mmbiz.qpic.cn/mmbiz_gif/n0NOdjkypXiccrnz7SvRYPwwblnYyZU2xHfzEt8V1LXPK6ibrQ9BaQ2YH7ZFx3CbYkgXbZeuPUc6PNrA57Fu2y8Q/640?wx_fmt=gif)

点击链接

[

100种分析思维模型（010号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477762&idx=1&sn=bfc400a41d0f344016de3529de612fef&chksm=8bf23410bc85bd06dcadc9c6d3ed9fd4bbda565f7808135ea5f5edb2eea6d626f2b037cfe6ae&scene=21#wechat_redirect)
[

100种分析思维模型（009号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477755&idx=1&sn=6097fc38a9d2aa0562d0aaca39cb9222&chksm=8bf234e9bc85bdffe674b108995697a94dd0a37b458bc589665fb7c3841c9f0b8b809dd0ec8f&scene=21#wechat_redirect)
[

100种分析思维模型（008号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477556&idx=1&sn=d2642afe4a49f020d73cc73b07b075a1&chksm=8bf23526bc85bc308847d3af71a3a222ec8c2c6217f236af64fbc931ceed96db10624eda8c7c&scene=21#wechat_redirect)

  

![](https://mmbiz.qpic.cn/mmbiz_png/iaOib7ro3AqzmN91fpfXS59xeURluqkMibVtr0e3xHBVBO500PJCI3ZftE81I2WiaClictvjqLE91j0mkUibSBXr1yug/640?wx_fmt=png)

关注林骥的公众号，更多干货早知道。
![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0IvXVY910XS9h5qCC6kuVt2ZPOUWUib2SrDxeYP8iawPXDOIDzPb0dUgtXtOj30gB0QqnxAM6iaEehw/640?wx_fmt=png)
欢迎加入我的  **免费** 知识星球，点击左下角的  阅读原文  即可加入。  如果你觉得文章对你有帮助或启发，麻烦你动动手指支持鼓励一下，
分享、收藏、点赞、  在  看，  谢谢！

#  ** ☟分享  ** ☟收藏  ** ****** ❤  ** ** ** ** ** ☟  ** ** 点赞 ☟  ** ** 在看  **

预览时标签不可点

微信扫一扫  
关注该公众号



轻触阅读原文

![](http://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3rBmMJ1emiaHxRCj3Om1wuZZCsgHvFSR3sVQrPsicIlRiaGUicJD8KCZibrmu0FzGBc6aBzfBz3HLIeDA/0?wx_fmt=png)

林骥







****



****



  收藏

