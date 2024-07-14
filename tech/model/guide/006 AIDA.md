![cover_image](https://mmbiz.qlogo.cn/mmbiz_jpg/giaycic3UNwo3x4RoFEEHg4f9CM2aGickfNajmlr1lHdHpgA7Dicn6icMXPbZiaKx7hib3TyPZetbhLjp6MTMMCn8hnqQ/0?wx_fmt=jpeg)

#  100种分析思维模型（006号）

原创  林骥  [ 林骥 ](javascript:void\(0\);)

**林骥**

微信号  linjiwx

功能介绍  《数据化分析》作者，从事数据分析工作 16 年，致力于用数据化解难题，让分析更加有效。

__ __

__ _ _ _ _

你好，我是林骥。  今天介绍第  006  号分析思维模型：  销售漏斗模型  。  1\. 模型介绍

1898 年，美国有一个叫 Elmo Lewis 的人，提出了 **漏斗模型** 的概念，后来被总结为 **AIDA** 模型，也称为「  **爱达**
」公式，首字母分别代表：

（1）注意 **A** ttention

（2）兴趣 **I** nterest

（3）欲望 **D** esire

（4）行动 **A** ction

从吸引客户的注意，到引起客户的兴趣，再到产生拥有的欲望，最后形成购买的行动，每个环节都会有客户流失，越靠后的环节，客户数量往往就越少，画出来的图形，就像一个漏斗。

2\. 应用举例

以常见的销售过程为例，我们可以把客户细分为目标客户、意向客户和订购客户：

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3x4RoFEEHg4f9CM2aGickfNoWIshfSf3snn87al6XVuSmIgL8h6mDZgMlaDkibxmZVDH1myia5PCUpQ/640?wx_fmt=jpeg)

从销售漏斗图的形状，我们就能比较直观地看到每个环节的转化情况。
通过横向或纵向的对比，发现业务中可能存在的问题，然后进一步分析原因，从而有针对性地提出解决问题的建议。  

**一个好的模型，可以促进沟通和行动，从而产生良性循环的好结果。**

你可以根据自身业务的实际情况，细分为更多的环节。

下面是用 Python 绘制销售漏斗图的代码：

    
    
    # 导入库  
    import pyecharts.options as opts  
    from pyecharts.charts import Funnel  
      
    # 定义数据  
    x_data = ['目标客户', '意向客户', '订购客户']  
    y_data = [100, 80, 20]  
    data = [[x_data[i], y_data[i]] for i in range(len(x_data))]  
      
    # 画漏斗图  
    c = (  
        Funnel(init_opts=opts.InitOpts(width="1000px", height="600px"))  
        .add(  
            # 系列名称  
            series_name="",  
            # 系列数据项  
            data_pair=data,  
            # 数据图形间距  
            gap=2,  
            # 标签配置项  
            label_opts=opts.LabelOpts(is_show=True, position="inside", font_size=18),  
            # 图元样式配置项  
            itemstyle_opts=opts.ItemStyleOpts(color='#00589F', border_width=1),  
        )  
        .set_global_opts(  
            # 设置标题  
            title_opts=opts.TitleOpts(title="销售漏斗模型", pos_left='center',   
                         title_textstyle_opts=opts.TextStyleOpts(font_size=26)),  
            # 隐藏图例  
            legend_opts=opts.LegendOpts(is_show=False)  
        )  
        .render("销售漏斗模型.html")  
    )

3\. 分析思考

在应用分析思维模型的时候，我们不要停留在问题的表面，而要透过现象看本质，思考模型背后的逻辑。

**（1）过程重于结果**

结果是由过程产生的，如果每个过程都做好了，那么结果通常不会太差。

比如说，如果把销售的每个阶段都做好了，目标客户定位精准，营销的转化率高，那么订购客户通常不会少。

**（2）预防重于纠错**

在问题发生之前，提前预测到可能出现的问题，并采取相应的预防措施，这比问题发生之后再进行纠错更加重要。

有一个「扁鹊三兄弟」的故事，据说扁鹊的大哥医术最高明，因为他能预防疾病的发生。

**（3）该说的要说到**

让过程变得制度化、规范化、程序化。

如果不能实行法治，那么过程就会变得随意。

**（4）说到的要做到**

凡是制度化的内容，都必须严格执行。

如果有制度却不执行，那么还不如没有制度。

**（5）做到的要见到**

凡是已经发生的过程，都要留下记录。

如果没有记录，那么就不利于管理决策。

**（6）让流程标准化**

在深入细致研究的基础上，借鉴优秀的经验，制定标准化的流程。

如果没有标准化的流程，那么就难以沉淀成功的经验。

小结

销售漏斗模型，是科学反映销售效率的一个模型，本质上是对销售过程的细化管理，可以帮助我们把流程标准化并沉淀下来。

最后，提醒一下：  任何一个分析思维模型，都不可能解决所有的问题  。
我们应该根据实际情况，把更多的时间和精力，用来灵活地选择和应用多种分析思维模型，从而做出更加科学的决策。

![](https://mmbiz.qpic.cn/mmbiz_gif/n0NOdjkypXiccrnz7SvRYPwwblnYyZU2xHfzEt8V1LXPK6ibrQ9BaQ2YH7ZFx3CbYkgXbZeuPUc6PNrA57Fu2y8Q/640?wx_fmt=gif)

  

点击下面链接

[

100种分析思维模型（005号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477360&idx=1&sn=be2c4457318600fd9b5702c061c63672&chksm=8bf23662bc85bf74762ea1476323160388ec0ee56df605c39c39f62448e52a8d6429e402ce58&scene=21#wechat_redirect)
[

100种分析思维模型（004号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477319&idx=1&sn=a5e8945da69db7cd14e76173694fbc73&chksm=8bf23655bc85bf4313685fc70a540c0f1febe17d5a1810a2ccba143992cfa5103a843f893dec&scene=21#wechat_redirect)
[

100种分析思维模型（003号）

](http://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477299&idx=1&sn=cdb2c2f2f7ac510f8de918f7dfca7b8c&chksm=8bf23621bc85bf37a4ed9ee9e808fe57101676478d3a572bf1820f3ee04ec3b552aa8119e1a7&scene=21#wechat_redirect)  

![](https://mmbiz.qpic.cn/mmbiz_png/iaOib7ro3AqzmN91fpfXS59xeURluqkMibVtr0e3xHBVBO500PJCI3ZftE81I2WiaClictvjqLE91j0mkUibSBXr1yug/640?wx_fmt=png)

关注林骥的公众号，更多干货早知道。
![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0IvXVY910XS9h5qCC6kuVt2ZPOUWUib2SrDxeYP8iawPXDOIDzPb0dUgtXtOj30gB0QqnxAM6iaEehw/640?wx_fmt=png)
欢迎加入我的  **免费** 知识星球，点击左下角的  阅读原文  即可加入。  如果你觉得文章对你有帮助或启发，麻烦你动动手指支持鼓励一下，
分享、收藏、点赞、  在  看，  谢谢！

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

