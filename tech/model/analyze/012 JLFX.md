![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo3qINDjrxAvTZib5lcficTGibwXFqeplDyeNPG31UVLV6Pm6qzDibVcn8S5Bc7Ebcko3dKQ9JApzdYEpA/0?wx_fmt=jpeg)

#  100种分析思维模型（012号）

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。

俗话说：物以类聚，人以群分。

今天介绍第 **012** 号分析思维模型： **聚类分析模型** 。

**1\. 模型介绍**

聚类分析，也被称为群分析，就是把一些原来没有分类的数据，通过某种算法，让相似的数据「 **聚** 」在一起，划分为不同的「 **类**
」，从而揭示出数据内在的特征和规律。

比如说，我们现在有客户的性别、年龄、地区等个人信息，还有 [ RFM
](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&scene=21#wechat_redirect
"RFM") 等购物信息，如果是要分析客户的购物特征，那么可以先排除客户的个人信息，只使用购物信息进行聚类，从而避免聚类结果被个人信息所影响。

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

**2\. 应用举例**

下面以 sklearn 中自带的鸢尾花数据集为例，对它进行聚类分析。

为了方便进行数据可视化，我们只选取数据集中的 2 个变量：花萼长度和花瓣长度。

  *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   * 

    
    
    # 导入相关库import numpy as npimport matplotlib.pyplot as pltfrom matplotlib.colors import ListedColormapfrom sklearn import datasetsfrom sklearn.cluster import KMeans  
    # 加载鸢尾花数据集iris = datasets.load_iris()  
    # 为了方便可视化，只选取 2 个特征X = iris.data[:, [0, 2]]  
    # 设置聚类的数量n_clusters = 3  
    # 调用 K-means 聚类算法km = KMeans(n_clusters)km.fit(X)  
    # 聚类的标签lbs = km.labels_  
    # 聚类的中心点cts = km.cluster_centers_  
    # 定义绘制决策边界的函数def plot_decision_boundary(model, axis):    # 生成绘图数据    x0, x1 = np.meshgrid(        np.linspace(axis[0], axis[1], int((axis[1]-axis[0])*100)).reshape(-1,1),        np.linspace(axis[2], axis[3], int((axis[3]-axis[2])*100)).reshape(-1,1)    )    X_new = np.c_[x0.ravel(), x1.ravel()]    # 用模型进行预测    y_predict = model.predict(X_new)    zz = y_predict.reshape(x0.shape)    # 定义颜色    custom_cmap = ListedColormap(['#EF9A9A','#FFF59D','#90CAF9'])    # 绘图    plt.contourf(x0, x1, zz, cmap=custom_cmap)   
    # 设置图形大小plt.figure(figsize=(8, 6))  
    # 绘制决策边界plot_decision_boundary(km, axis=[3, 8, 0, 8])  
    # 绘制散点图for c in range(n_clusters):    plt.scatter(X[lbs == c, 0], X[lbs == c, 1])  
    # 画出每个聚类的中心点plt.scatter(cts[:, 0], cts[:, 1], marker='*', c='r', alpha=0.9, s=200)  
    # 显示图形plt.show()

运行代码，结果如下：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo0c2xTbl0MdLpOYqGR1sOVm8uHD8HrCcT6qF3lWS68wto5CB2wiaAFy0buErGwWAGhc4rhicGpzyVrw/640?wx_fmt=jpeg)

其中不同的颜色代表不同的类别，红色的五角星符号代表聚类的中心点。

**最后的话**

做聚类分析的时候，首先要考虑解决的问题是什么，然后再选择适当的变量进行聚类。

最后，我们一定要记住： **不要脱离业务问题谈模型，而要让模型更好地为业务决策服务。** ****

![](https://mmbiz.qpic.cn/mmbiz_gif/n0NOdjkypXiccrnz7SvRYPwwblnYyZU2xHfzEt8V1LXPK6ibrQ9BaQ2YH7ZFx3CbYkgXbZeuPUc6PNrA57Fu2y8Q/640?wx_fmt=gif)

  

往期推荐

[

100种分析思维模型（011号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477819&idx=1&sn=b8aabdb1e2511fe5829bb75880036be4&chksm=8bf23429bc85bd3fae054f2b5e41d1ff704a1d2a1a33c647b11632a4ed98eb38edd79fce5c7f&scene=21#wechat_redirect)
[

100种分析思维模型（010号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477762&idx=1&sn=bfc400a41d0f344016de3529de612fef&chksm=8bf23410bc85bd06dcadc9c6d3ed9fd4bbda565f7808135ea5f5edb2eea6d626f2b037cfe6ae&scene=21#wechat_redirect)
[

100种分析思维模型（009号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477755&idx=1&sn=6097fc38a9d2aa0562d0aaca39cb9222&chksm=8bf234e9bc85bdffe674b108995697a94dd0a37b458bc589665fb7c3841c9f0b8b809dd0ec8f&scene=21#wechat_redirect)

  

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

