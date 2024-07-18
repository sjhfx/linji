一个分析思维模型的背后，可能涉及很多相关的背景知识，但对于使用模型的人来讲，真正关心的是如何应用模型去解决实际的问题，而不是模型背后复杂的原理和公式。

这就好比使用手机和电脑，我们关心的是其中软件的应用和运行的速度，并不需要理解计算机的原理和算法。

我选择 **100** 种分析思维模型的原则，也是 **侧重于应用** ，而不是原理。

希望我能用简单朴素的方式，把自己学习、思考和实践过程中，总结出来的有价值的信息，分享和传递出去，让更多的人能够从中受益。

**1. 模型介绍**

波士顿咨询公司的创始人布鲁斯·亨德森，于 1970 年创建了一种矩阵分析模型，他选择两个重要的指标，分别作为二维坐标的横轴和纵轴，形成一个具有四个象限的矩阵，所以通常称之为波士顿矩阵，也称为四象限分析法。

波士顿矩阵通常用来分析产品结构，其中包括两个重要的指标，分别是： **销售增长率** 和 **市场占有率** ，把产品分成 4 种类别，建议采取不同发展策略，从而实现产品结构的良性循环。

**（1）明星类产品 ★：加大投资**

**（2）问题类产品 ? ：选择策略**

**（3）金牛类产品 ￥：保持现状**

**（4）瘦狗类产品 × ：逐步放弃**

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo16IGZE7oNELWnKic6V4A73okflGmp9P5RtvLEUgcg4QR7RSzibsMhPzTUL2suLfJVjJZa5O6DENm4g/640?wx_fmt=jpeg) 

应用矩阵分析模型的步骤：

（1）提炼两个重要的指标；

（2）绘制四象限分析图表；

（3）分析总结和提出建议。

**2. 应用举例**

矩阵分析模型的应用非常广泛，只要你能找到两个关键指标，就可以试着应用它来进行分析。

比如说，我在免费的知识星球「林骥」分享过一个超市数据集，其中包含每个地区的销售额、数量、折扣和利润等数据，我们可以从中提炼出两个重要的指标：销售额和利润率，然后绘制四象限分析图表。

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo16IGZE7oNELWnKic6V4A73ocTpGGE5mGAEF8XfcUqO8b0mqGWjRUNsop1cbdQCqic0zdYYmnt4c6icw/640?wx_fmt=jpeg) 

根据上面的销售额与利润率分析矩阵，我们可以结合对业务实际情况的理解，分析总结业务的亮点和不足，从而有针对性提出有用的建议。

比如说，华北地区的利润率最高，但是销售规模一般，可以试着分析总结华东地区的销售经验，用来提升华北地区的销售额，同时让利润率保持在较高的水平，从而提升企业整体的利润。

下面是完整的 Python 代码：

```python # 导入所需的库

import numpy as np import pandas as pd import matplotlib.pyplot as plt 

# 正常显示中文标签

plt.rcParams['font.sans-serif'] = ['SimHei']

# 读取 Excel文件

df_excel = pd.read_excel('../../data/超市数据.xlsx') 

# 数据透视表

df = df_excel.pivot_table(values=['销售额', '利润'], index='地区', aggfunc=sum) 

# 计算利润率

df['利润率'] = round(df['利润']/df['销售额']*100, 1) 

# 使用「面向对象」的方法画图，定义图片的大小

fig, ax = plt.subplots(figsize=(8, 8)) 

# 设置背景颜色

fig.set_facecolor('#00589F') 

# 设置标题

ax.set_title('\n销售额与利润率分析矩阵\n', loc='center', size=26, color='w') 

# 基础散点图：这里需要单独拆开 x，y 轴和希望配对的标签

x, y = df['销售额']/10000, df['利润率']

label = df.index 

# 画散点图

ax.scatter(x, y, color='#00589F', marker='.', s=600, zorder=1) 

# 设置坐标标签字体大小和颜色

ax.tick_params(labelsize=13, colors='#cccccc') 

# 设置坐标轴的标题

ax.text(ax.get_xlim()[0]-120, np.mean(ax.get_ylim()), '利\n润\n率\n(%)', va='center', ha='center', fontsize=16, color='w') ax.text(np.mean(ax.get_xlim()), ax.get_ylim()[0]-9, '销售额(万元)\n', va='center', ha='center', fontsize=16, color='w') 

# 对散点图中的每一个点进行文字标注

for a,b,l in zip(x,y,label):

    plt.text(a, b+0.5, '%s' % l, ha='center', va='bottom', fontsize=16) 

# 设置坐标轴范围，根据数据情况进行适当修改

ax.set_xlim(0, round(x.max(), -2)) ax.set_ylim(0, round(y.max(), -1)) 

# 添加特定分割线，在变量的均值处开始画

plt.vlines(x=x.mean(), ymin=0, ymax=ax.get_ylim()[1], colors='#999999', linewidth=1) plt.hlines(y=y.mean(), xmin=0, xmax=ax.get_xlim()[1], colors='#999999', linewidth=1) 

# 隐藏背景网格

plt.grid(False) 

plt.show() ```

**最后的话**

矩阵分析模型，比较简单直观，没有复杂的理论公式，关键是理解它的分析思维，用自己积累的知识经验，找到两个重要的指标，对它们进行深入的分析，从而解决实际的问题。

矩阵分析模型的应用非常广泛，不仅能用来分析产品和销售，而且还能用来做[人群划分](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653473967&idx=1&sn=544e23b9861f3fbf57a05c915b8bac99&scene=21#wechat_redirect) ，甚至可以用来[实现梦想](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653474951&idx=1&sn=e4309585da5b8697e3255d0ce15a98ad&scene=21#wechat_redirect) ，等等。

合理地应用矩阵分析模型，能够帮助我们更好地抓住问题的关键，更深刻地理解关键指标之间的联系，提高我们分析思维能力，从而提出更有前瞻性的建议，帮助我们作出更加科学的决策。

更新：2024-07-18

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)