# 客户生命周期

客户作为一个有生命的个体，有哪些特点？

**客户生命周期模型**能帮我们更好地理解客户，从而有利于营销活动的策划和运营管理的决策。

## **1. 模型介绍**

每个生命，都有一个从出生到死亡的过程。

客户生命周期，是指客户从第一次购买到最后一次购买间隔的时间。

结合以前介绍过的 [RFM 分析模型](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&scene=21#wechat_redirect "RFM 分析模型") ，我们可以把客户生命周期分成不同的阶段。

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

## **2. 应用举例**

我们以 Tableau 自带的超市数据集为例，对客户生命周期进行数据可视化的分析。

**（1）打开数据源**

首先，用 Tableau 打开软件自带的【示例 - 超市】数据。

**（2）创建计算字段**

其次，创建几个相关的计算字段。

【R 间隔天数】

{  FIXED [客户名称]  :  

DATEDIFF  (  'day'  ,  MAX  ( [订单日期]  ),  DATE  (  "2021-12-31  "))}

【F 累计购买次数】

{  FIXED [客户名称]  :  COUNTD  ( [订单 Id]  )}

【L 生命周期】

{  FIXED [客户名称]  :  

DATEDIFF  (  'day'  ,  MIN  ( [订单日期]  ),  MAX  ( [订单日期]  ))}

【C 客户分类】

IF [R 间隔天数]  >= 720 THEN  '6流失客户'  

ELSEIF [R 间隔天数]  >= 360 THEN  '5休眠客户'  

ELSEIF [F 累计购买次数]  < 4 THEN  '1新生客户'  

ELSEIF [F 累计购买次数]  < 7 THEN  '2有效客户'  

ELSEIF [F 累计购买次数]  < 10 THEN  '3活跃客户'  

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

## **最后的话**

客户作为一个人，往往都具有多面性。

理解客户，本质就是要洞察和满足客户的需求。

如果按照客户生命周期来划分客户，那么有助于我们理解不同阶段的客户需求，从而有针对性地采取运营策略，在成本可控的前提下，尽可能延长客户的生命周期。

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)