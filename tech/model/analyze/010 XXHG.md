![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo1Hic0cMMOzlzqPd7ZG1K4u9CkPibPgOSxicU3wEypLJlCEVlvibFXibmNN5qxDgWPhru9fd6g1iafHG4Gg/0?wx_fmt=jpeg)

#  100种分析思维模型（010号）

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。

数据分析的最终目的是为了辅助决策，从而创造价值。

今天介绍的第 **010** 号分析思维模型： **线性回归模型** ，能帮助我们做出更好的决策。

**1\. 模型介绍**

线性回归是指利用线性的方法，研究不同变量之间的关系。例如：广告费与商品销量之间的关系。

需要注意的是，通过线性回归找到的关系，可能只是一种相关关系，并不一定是因果关系。

因果关系的判定，需要建立在经过实践检验的理论基础之上。

比如说，根据经济学的需求定律，当其他变量保持不变的时候，一种商品的需求量，依赖于该商品的价格，当价格越高，需求量往往越低。

为了方便起见，我们通常用  表示应变量，  表示自变量。

最简单的线性回归，是一元线性回归，可以用数学方程表示为：

如果用图形画出来，那么显示的是一条直线。

**2\. 应用举例**

线性回归模型的应用十分广泛，它可以帮我们找到不同变量之间的关系，为数据分析的「大胆假设」提供良好的基础。

以广告费与商品销量的数据为例，用 Python 实现线性回归的代码如下：

    
    
    # 导入所需的库  
    import numpy as np  
    import pandas as pd  
    import matplotlib as mpl  
    import matplotlib.pyplot as plt  
    from sklearn.linear_model import LinearRegression  
    from sklearn.preprocessing import PolynomialFeatures  
    from sklearn.pipeline import Pipeline  
      
    # 正常显示中文标签  
    mpl.rcParams['font.sans-serif'] = ['SimHei']  
      
    # 数据源路径：https://t.zsxq.com/jEEqB6e  
    filepath='./data/广告费与商品销量.xlsx'  
      
    # 读取 Excel文件  
    df = pd.read_excel(filepath, index_col='日期')  
      
    # 定义画图用的数据  
    df_group = df.groupby('广告费').mean()  
    x = np.array(df_group.index).reshape(-1, 1)  
    y = np.array(df_group.values)  
      
    # 用管道的方式调用算法，以便把线性回归扩展为多项式回归  
    poly_reg = Pipeline([  
        ('ploy', PolynomialFeatures(degree=1)),  
        ('lin_reg', LinearRegression())  
    ])  
      
    # 拟合  
    poly_reg.fit(x, y)  
      
    # 斜率  
    coef = poly_reg.steps[1][1].coef_  
    # 截距  
    intercept = poly_reg.steps[1][1].intercept_  
    # 评分  
    score = poly_reg.score(x, y)  
      
    # 使用「面向对象」的方法画图，定义图片的大小  
    fig, ax = plt.subplots(figsize=(8, 6))  
      
    # 标注公式  
    formula = r'$y = ' + '%.2f' % coef[0][1] + 'x' + '%+.2f$' % intercept[0] + '，' + r'${R}^2 = ' + '%.5f$' % score  
      
    # 设置标题  
    ax.set_title('广告费每增加1万元，商品销量增加' + '%.0f' % (coef[0][1]) + '个\n'+formula, loc='left', size=26)  
      
    # 画气泡图  
    ax.scatter(x, y, color='#00589F', marker='.', s=100, zorder=1)  
      
    # 绘制预测线  
    y2 = poly_reg.predict(x)  
    ax.plot(x, y2, '-', c='#5D9BCF', zorder=2)  
      
    # 隐藏边框  
    ax.spines['top'].set_visible(False)  
    ax.spines['right'].set_visible(False)  
      
    # 设置坐标标签字体大小和颜色  
    ax.tick_params(labelsize=16)  
      
    # 设置坐标轴的标题  
    ax.text(ax.get_xlim()[0]-1.2, ax.get_ylim()[1]/2, '商\n品\n销\n量', va='center', fontsize=16)  
    ax.text(ax.get_xlim()[1]/2, ax.get_ylim()[0]-100, '广告费', ha='center', fontsize=16)  
      
    plt.show()  
    

运行之后，得到的图表如下：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo21FEicNia56ITKlibO3gFuP3WBcwMkkocibrH8hgJuiauTC4WaKXt2Zw2AJyClVRpIFibACUYMIlgNf5LQ/640?wx_fmt=jpeg)

从图中可以直观地看出，广告费与商品销量具有很强的线性关系，运用线性回归方程，可以根据广告费的预算，大致估计出商品的销量，这有助于制订更加合理的销售目标。

有经验的数据分析师，在提出建议的时候，会给出多个选项，比如说，如果投入这么多的资源，那么预期目标产出可以这么多；如果想减少资源的投入，那么预期目标产出可以那么多。这样领导在做决策的时候，会舒服很多。

需要注意的是，线性回归有其适用的范围，比如说，商品的销量并不能无限地增加，  当广告费增大到一定程度时  ，销量的增长  速度肯定会放缓。

**最后的话**

数据分析在「大胆假设」的基础上，我们一定要「小心求证」。

虽然线性回归模型很有用，但是我们要避免直线思维，因为现实中有很多事情，其实并不是按照直线的规律来发展的。

比如说，新冠病毒的传播，刚开始很多人以为感染的人数不多，没有引起足够的重视，结果付出了惨重的代价。

截止2021年3月21日，全球已经有超过1.2亿人感染了新冠病毒，累计死亡超过270万人，而且这个数字还在继续增长。

为了克服直线思维的本能，对于潜在的巨大风险，我们一定要保持高度的警惕。

随着技术的快速发展，工具应用类的技术门槛将变得越来越低，很多人的职业都将被机器人取代。

学习、思考、实践 100 种分析思维模型  ，积极应对未来的变化，  是我应对潜在风险的一种策略。  

![](https://mmbiz.qpic.cn/mmbiz_gif/n0NOdjkypXiccrnz7SvRYPwwblnYyZU2xHfzEt8V1LXPK6ibrQ9BaQ2YH7ZFx3CbYkgXbZeuPUc6PNrA57Fu2y8Q/640?wx_fmt=gif)

点击链接

[

100种分析思维模型（009号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477755&idx=1&sn=6097fc38a9d2aa0562d0aaca39cb9222&chksm=8bf234e9bc85bdffe674b108995697a94dd0a37b458bc589665fb7c3841c9f0b8b809dd0ec8f&scene=21#wechat_redirect)
[

100种分析思维模型（008号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477556&idx=1&sn=d2642afe4a49f020d73cc73b07b075a1&chksm=8bf23526bc85bc308847d3af71a3a222ec8c2c6217f236af64fbc931ceed96db10624eda8c7c&scene=21#wechat_redirect)
[

100种分析思维模型（007号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477503&idx=1&sn=49d9b1e1355358a85a3ae15198ff2757&chksm=8bf235edbc85bcfb903fc46f98af249252a5265179fd88593c72172105424670f94e00dd9900&scene=21#wechat_redirect)
[

100种分析思维模型（006号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477417&idx=1&sn=f12ee0f36a8b459060dcb517088b22d8&chksm=8bf235bbbc85bcadf8b2ae77e3ec9e146ca3ae03a294f5d76d021a57b59030ef1685debd50cc&scene=21#wechat_redirect)
[

100种分析思维模型（005号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&chksm=8bf23662bc85bf74762ea1476323160388ec0ee56df605c39c39f62448e52a8d6429e402ce58&scene=21#wechat_redirect)

  

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

