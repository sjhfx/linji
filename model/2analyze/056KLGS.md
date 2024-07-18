**1. 为什么学习** **凯利公式** **？**

 

在 [泊松分布](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653481775&idx=1&sn=33b68b6fda59248f0f65384c26a417f4&scene=21#wechat_redirect)这篇文章下面，有位读者留言说「很棒、很精彩、很实用」，并让我有机会讲讲凯利公式。  感谢这位读者的肯定，这是我持续分享的最大动力之一。

我研究了一下，凯利公式主要被用于赌博和投资领域，数学家爱德华·索普（Edward Thorp）曾经应用凯利公式，在赌场赚了几十万美元，并且写了一本名为《击败庄家》的书。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlP0gp2hLz197LKlscDQtoavYxYIDHInf5HRRQvHPK5y7iab5LMOM5ibfwQ/640?wx_fmt=png) 

但是赌场也不傻，不会坐以待毙，把索普列入黑名单，并修改了 21 点游戏的规则，于是重新确立概率优势。对普通人来说，要想不输给赌场，最好的选择还是不赌。

投资和赌博有很多相似的地方，都需要运用 [概率思维](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653481757&idx=1&sn=7cb6463421d3dbfbffd54eeff6e7d3f0&scene=21#wechat_redirect)和 [博弈思维](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653481782&idx=1&sn=4ed75fcc18c42eb0a22b8582452559f1&scene=21#wechat_redirect)，且需要平衡风险、收益、成本和时间。后来，索普转战华尔街，并且写了一本名为《战胜市场》的书。

我本人不参与赌博，也不购买股票，在投资方面只花了很少的时间和精力，主要是定投低成本的指数基金，只要能跟上市场的平均收益，我就感到心满意足了。

**我学习凯利公式，其实不是为了赌博，也不是为了购买股票，而是为了理解并运用它背后的思维模式，在风险、收益、成本和时间之间取得某种平衡，当面临重大选择的时候，可以做出更加科学、客观、理性的决策。**

无论在工作中，还是在生活中，通过掌握凯利公式背后的思维模式，可以提升决策的质量，进而提高工作的效能，让生活变得更加美好。  

**2. 什么是凯利公式？**

 

为了易于理解，下面我们用一个例子来说明凯利公式的含义。  假设有一种游戏，玩家获胜的概率是 60%，只要玩家身上还有钱，就可以一直玩下去，且每次都可以下注任意金额。游戏的规则是每下注 1 元，获胜就赚到 1 元，失败就输掉 1 元。

在不考虑借钱的情况下，如果玩家的初始资金是 100 元，那么请问：玩家应该如何下注，才能使得长期收益最大化？  

1956 年，物理学家约翰·拉里·凯利（John Larry Kelly）经过严密的推理计算，得出一个公式：

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlPIrU76lrTeO6Tor5mFIegtlIn62ZG4Oo0mRqUO2SLZM0HibKW62XHDgA/640?wx_fmt=png) 

其中 **f** 是最优下注比例  ，  **b** 是赔率 = 获胜赚到的钱 / 失败输掉的钱  ， **p** 是获胜的概率， **q** 是失败的概率。  按照上面的凯利公式，只要知道  赔  率  和  获胜的概率，就能算出应该投资多大的比例，获得最高的复利增长率，且不会输掉全部的本金。

比如，在上面的例子中，获胜的概率为 60%，失败的概率为 40%，赔率为 1 : 1 = 1，按照凯利公式，最优下注比例为 20%。  **凯利公式**

**的本质，是着重考虑长期累积的效果，在风险与回报之间找到一个平衡点，既能避免过度冒险，也能避免过度保守，以最大化长期收益。** 1965 年，凯利突然死于脑溢血，年仅 41 岁。  

据说，凯利本人从未使用他的公式来赚钱，但后人因为凯利公式而记住了他。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlP5lRSTomiakz4FTGcMjyx9ibiaTfYXEAiaQVKs7PVBiczicRWDb2Ork9UpYng/640?wx_fmt=png) 

**3. 怎么运用凯利公式？**

 

基于历史数据和专业的判断，我们可以通过分析和研究，预估赔率和

获胜的概率，然后就可以运用凯利公式，计算出最优投资比例。  

借助 GPT，用 Python 演示不同投资比例对最终收益的影响，给 ChatGPT 发送以下指令：

> 假设有一种游戏，玩家获胜的概率是 60%，只要玩家身上还有钱，就可以一直玩下去，且每次都可以下注任意金额，规则是每下注 1 元，获胜就赚到 1 元，失败就输掉 1 元。 

>  

>  在不考虑借钱的情况下，如果玩家的初始资金是 100 元，那么请问：玩家应该如何下注，才能使得长期收益最大化？  

> 

>  请用 Python 编程模拟这个赌局，并且每次下注 99%，看看下注 100 次的结果会怎么样？用图表显示出来，标签和标题用中文，设置图片的大小比例，设置字体和坐标轴数字的大小，并让网格线只显示横向的。

结果会生成一段 Python 代码，稍作修改如下：

```python import random import matplotlib.pyplot as plt 

plt.rcParams['font.family'] = 'SimHei'

initial_capital = 100  # 初始资金

win_probability = 0.6  # 赢的概率

loss_probability = 0.4  # 输的概率

bet_ratio = 0.99  # 下注比例：分别设置为 0.99、0.01、0.2 num_bets = 100  # 下注次数

capital = initial_capital capital_history = [capital]

for _ in range(num_bets):

    bet_amount = capital * bet_ratio 

    # 模拟赌博结果

    if random.random() < win_probability:

        capital += bet_amount     else:

        capital -= bet_amount 

    capital_history.append(capital) 

# 设置图表的大小比例

plt.figure(figsize=(10, 6))     

# 绘制资金变化折线图

plt.plot(range(num_bets+1), capital_history) plt.xlabel('下注次数', fontsize=16) plt.ylabel('资金金额', fontsize=16) plt.title('资金金额随着下注次数的变化', fontsize=20) plt.tick_params(axis='both', which='major', labelsize=15) plt.grid(axis='y') # 只显示纵轴上的网格线

# 显示图表，由于结果是随机的，所以每次运行得到的图表可能会有所不同

plt.show() ```

假设张大胆每次下注比例为 99%，赢钱时可以赢得很多，但输钱时也输得厉害，只要输一次，就会让本金很快接近于 0，几乎是面临「灭顶之灾」，而且后面不大可能翻身。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlPiaoEEQJAZvx1yu684ed7M73ZR7OPXsbMoIboxvhwIa86CzIE2DNzBdg/640?wx_fmt=png) 

假设王保守每次下注比例设置为 1%，虽然这样做确实很安全，但是资金增长将会非常缓慢，不符合长期收益最大化的原则。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlPM9d9lqr0s3tr76TgGHS9coAmVfibOFMKt8Fa1WUc1WTvk4icP7CkuicSQ/640?wx_fmt=png) 

假设你运用凯利公式，每次下注比例设置为 20%，长期来看收益最大。模拟下注 100 次之后，资金可能超过 12000 元，是初始资金的 120 多倍。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo0YjBCcq1jibKybz4QHROBlPf26ibgzcIJqWkPfsBLjHicsr22a3AnpbuC5rKtuXiamVrJaNuo49ajtxQ/640?wx_fmt=png) 

凯利公式在金融领域的应用非常广泛，很多著名的投资人都承认自己用过凯利公式，包括股神沃伦·巴菲特、股神搭档查理·芒格、债券之王比尔·格罗斯等。

查理·芒格说过：

> 当世界给予你机会的时候，聪明的投资者会下重手。当他们具有极大赢面的时候，他们会下大注。其余的时间里，他们做的仅仅是等待，就这样简单。

**凯利公式** **背后的思维方式，其实比公式本身更加重要。** 我们可以把凯利公式应用到实际工作中，做出大概率正确的决策，以提升决策的有效性。

比如，当升职加薪的机会很大时，不妨在工作中投入更多的时间和精力，努力去拼搏一把。

但是，也要注意适当留有余地，该休息时还是要休息，不要以牺牲生命为代价，否则得不偿失。  

**人生就像一场拉力赛，当直线加速的时候，确实要一脚油门踩到底。但是，当遇到弯路的时候，也要懂得及时踩刹车，以确保人身安全。**

在运用凯利公式的时候，不要因为关注具体的数据指标，而忘了真正的目标。就像开车的时候，真正的目标是在远方，而不是在仪表盘的数字上。  

**最后的话**

作为一个理性的人，应该多做大概率正确的事，而不要有赌徒的心态——赢的时候迷信手气而加大投入，输的时候则期望下一把翻本。

世界充满了不确定性，有时候失败的概率虽然很低，但失败之后的结果可能非常严重。  美国有一家公司，曾经是华尔街的超级梦之队，刚开始每年的收益率高达 30% 以上，但它的高收益是建立在高杠杆、高风险的基础之上，一旦市场下跌 3%，本金就会全部亏光。

虽然经过知名经济学家的精心测算，从理论上来说，亏光的概率非常小，估计不到万分之一，但这种小概率事件恰恰就发生了。1998 年，这家公司在不到 4 个月的时间内，就亏掉了 46 亿美元，随后倒闭。

**面对不确定性，我们要始终保持理性，不要高估获胜的概率，而要对风险保持敬畏，持续学习，并应用所学的知识，去解决一些重要的问题，这是获得成功的关键。**

特别声明：本文内容不代表任何投资建议，仅供参考。 

延伸阅读：  

《击败庄家》  

《战胜市场》  

《战胜一切市场的人》

![PageViews](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)