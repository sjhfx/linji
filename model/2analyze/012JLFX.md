俗话说：物以类聚，人以群分。

下面介绍**聚类分析模型** 。

## **1. 模型介绍**

聚类分析，也被称为群分析，就是把一些原来没有分类的数据，通过某种算法，让相似的数据「 **聚** 」在一起，划分为不同的「 **类**

」，从而揭示出数据内在的特征和规律。

比如说，我们现在有客户的性别、年龄、地区等个人信息，还有 [RFM](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&scene=21#wechat_redirect "RFM") 等购物信息，如果是要分析客户的购物特征，那么可以先排除客户的个人信息，只使用购物信息进行聚类，从而避免聚类结果被个人信息所影响。

当我们得到聚类结果之后，可以再结合客户的个人信息，把客户分成若干个不同的类别，给客户打上相应的标签，按照二八法则，识别出优质客户，提供个性化的服务，从而为客户创造价值。

聚类分析属于一种无监督学习，类似于我们认知事物的过程。

当我们面临大量未知的事物时，可以通过寻找其中的规律，挖掘数据内部的分布特性，反映出数据之间的异同，从而建立一套划分的方法，让我们更加深入地了解事物的内在特征，从而提高了我们认知事物的能力。

比如说，当你进入一个陌生的群体时，没有人帮你介绍，你根据外貌、性格、行为等方面，将不同的人划分为不同的类别，并根据经验来定义类别的标签，例如：高富帅、白富美、谨慎型、外向型、体贴型等等。

这个过程就属于无监督学习，因为事先无人教你。

而对于监督学习，就好像有一位老师在旁边教你，这位老师对群体里面的每一个人都很熟悉，他会向你介绍每一个人，帮你先做好了分类，并且贴好了标签。

但是，当老师提供的信息有误时，就会导致你的认知出现偏误。

假如来了一个「异类」，不属于老师所介绍的任一类型，那么就会导致你无法做出正确的判断。

聚类分析模型在很多学科都有重要的应用，包括数学、统计学、计算机科学、经济学和生物学等等。

在商业上，可以用来发现不同的客户群体；在生物上，可以用来对动植物和基因进行分类。

## **2. 应用举例**

下面以 sklearn 中自带的鸢尾花数据集为例，对它进行聚类分析。

为了方便进行数据可视化，我们只选取数据集中的 2 个变量：花萼长度和花瓣长度。

```python # 导入相关库

import numpy as np import matplotlib.pyplot as plt from matplotlib.colors import ListedColormap from sklearn import datasets from sklearn.cluster import KMeans 

# 加载鸢尾花数据集

iris = datasets.load_iris() 

# 为了方便可视化，只选取 2 个特征

X = iris.data[:, [0, 2]]

# 设置聚类的数量

n_clusters = 3 

# 调用 K-means 聚类算法

km = KMeans(n_clusters) km.fit(X) 

# 聚类的标签

lbs = km.labels_

# 聚类的中心点

cts = km.cluster_centers_

# 定义绘制决策边界的函数

def plot_decision_boundary(model, axis):

    # 生成绘图数据

    x0, x1 = np.meshgrid(

        np.linspace(axis[0], axis[1], int((axis[1]-axis[0])*100)).reshape(-1,1),

        np.linspace(axis[2], axis[3], int((axis[3]-axis[2])*100)).reshape(-1,1)     )     X_new = np.c_[x0.ravel(), x1.ravel()]

    # 用模型进行预测

    y_predict = model.predict(X_new)     zz = y_predict.reshape(x0.shape)     # 定义颜色

    custom_cmap = ListedColormap(['#EF9A9A','#FFF59D','#90CAF9'])     # 绘图

    plt.contourf(x0, x1, zz, cmap=custom_cmap) 

# 设置图形大小

plt.figure(figsize=(8, 6)) 

# 绘制决策边界

plot_decision_boundary(km, axis=[3, 8, 0, 8]) 

# 绘制散点图

for c in range(n_clusters):

    plt.scatter(X[lbs == c, 0], X[lbs == c, 1]) 

# 画出每个聚类的中心点

plt.scatter(cts[:, 0], cts[:, 1], marker='*', c='r', alpha=0.9, s=200) 

# 显示图形

plt.show() ```

运行代码，结果如下：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo0c2xTbl0MdLpOYqGR1sOVm8uHD8HrCcT6qF3lWS68wto5CB2wiaAFy0buErGwWAGhc4rhicGpzyVrw/640?wx_fmt=jpeg) 

其中不同的颜色代表不同的类别，红色的五角星符号代表聚类的中心点。

## 

## **最后的话**

做聚类分析的时候，首先要考虑解决的问题是什么，然后再选择适当的变量进行聚类。

最后，我们一定要记住： **不要脱离业务问题谈模型，而要让模型更好地为业务决策服务。**

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)