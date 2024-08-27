**1. 模型介绍**

1898 年，美国有一个叫 Elmo Lewis 的人，提出了 **漏斗模型** 的概念，后来被总结为 **AIDA** 模型，也称为「  **爱达**

」公式，首字母分别代表：

（1）注意 **A** ttention 

（2）兴趣 **I** nterest 

（3）欲望 **D** esire 

（4）行动 **A** ction 

从吸引客户的注意，到引起客户的兴趣，再到产生拥有的欲望，最后形成购买的行动，每个环节都会有客户流失，越靠后的环节，客户数量往往就越少，画出来的图形，就像一个漏斗。

## **2. 应用举例**

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

## **最后的话**

销售漏斗模型，是科学反映销售效率的一个模型，本质上是对销售过程的细化管理，可以帮助我们把流程标准化并沉淀下来。

最后，提醒一下：  任何一个分析思维模型，都不可能解决所有的问题  。

我们应该根据实际情况，把更多的时间和精力，用来灵活地选择和应用多种分析思维模型，从而做出更加科学的决策。

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)