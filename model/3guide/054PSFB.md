在前面的 [100 种分析思维模型](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzA4ODE2OTIxMw==&action=getalbum&album_id=1701638273011351554#wechat_redirect) 系列文章中，曾经介绍过 [正态分布](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477503&idx=1&sn=49d9b1e1355358a85a3ae15198ff2757&scene=21#wechat_redirect) 、 [幂律分布](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653477556&idx=1&sn=d2642afe4a49f020d73cc73b07b075a1&scene=21#wechat_redirect) ，下面再介绍另外一种应用广泛的概率分布模型： **泊松分布** 。

**1.为什么学习** **泊松分布** **？**

概率分布就像一个工具箱，泊松分布就是工具箱里的一种工具。当我们研究一个现象的时候，不妨运用假设思维，先大胆假设服从某种概率分布，然后再小心求证这个假设，以便从工具箱中找适合的工具。

你只有选择符合实际情况的概率分布，才能更好地预测未来，否则就有可能会出错。这就好比你在钉钉子的时候，选择的工具最好是锤子，而不是菜刀，否则就容易伤到手。

**学习** **泊松分布**

**的原理和运用方法，可以帮助我们从整体上把握随机事件发生的规律，完善我们对随机性的认识，以便做出更加准确的预测和决策，特别是提高风险防范的意识，更好地解决一些现实世界的问题。**

比如，在购买保险的时候，很多人觉得小公司服务好，而且承诺同样的赔偿，于是选择小的保险公司，但事实上，万一遇到需要大额索赔的时候，有些小的保险公司是赔不出来的，其实就没能真正起到保险的作用。

在管理水平和效率差不多的情况下，保险公司的规模越大，风险往往就越小。因此，运用概率思维，我们应该优先考虑选择大的保险公司进行投保，避免花冤枉钱。

**2. 什么是** **泊松分布** **？**

 ** 泊松分布最初是由法国数学家西莫恩·德尼·泊松（Siméon-Denis Poisson）在

1838 年提出来的，用于描述小概率事件的分布规律，比如机器故障、自然灾害等，事件的发生是相互独立的，且概率在时间或空间上是均匀分布的。  ** **

![](https://mmbiz.qpic.cn/mmbiz_jpg/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibzVArOOMOu1F2k5GAv2ReSjYowbsQYnWtFM5BusRH5Viak0YXl2YnrVSw/640?wx_fmt=jpeg) ** 假设随机事件发生的概率是 p，进行 n 次独立的试验，发生 k 次的概率为：

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibztDib0VzH5j2ossMZ7NtKsC63MTPKBpxyY0D30WgibEC6kXwa08mesveg/640?wx_fmt=png) 这个公式看起来比较复杂，但是相当优美，而且用计算机算起来还是比较简单的。  其中 e 是自然常数，约等于 2.718。k 为事件发生的次数，等于 0, 1,

2 ……  其中 λ 是单位时间内平均发生的次数，当 n 很大而 p 很小时，泊松分布可作为二项分布的近似，λ = n*p。  其中 !

是数学中的阶乘符号，定义 0! = 1，n! = n*(n-1)!，以此类推。比如，3! = 3*2*1 = 6。  假设一台机器平均每小时出故障的概率是

0.03%，如果想知道接下来 10000 小时发生故障的概率，那 λ 就等于 10000*0.03% = 3 次。  当 k = 0 时，P(X = 0) 就代表接下来 10000 小时不发生故障的概率，运用上面的计算公式，计算结果约等于 5%。也就是说，这台机器在 10000 小时内至少发生 1 次故障的概率高达 95%。  有些机器一旦发生故障，可能事关重大，甚至涉及生命安全。比如，在高速上行驶的汽车，刹车系统一旦失灵，就有可能造成严重的交通事故。

不怕一万，就怕万一。所以，对于一些非常重要的机器，务必要定期进行检查，提前预防意外事件的发生。

**3.怎么运用** **泊松分布** **？**

为了简化计算的过程，我们可以借助 [GPT](https://mp.weixin.qq.com/s?__biz=MzA4ODE2OTIxMw==&mid=2653481745&idx=1&sn=100d8717c3a4a973871dd104e18a03ba&scene=21#wechat_redirect) 来计算泊松分布的概率，给 ChatGPT 发送以下指令：

> 对于泊松分布，假设随机事件发生的概率是 0.03%，进行 10000 次独立的试验，至少发生 1 次的概率是多少？

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibzcYGq0MicZL4HlTro5AutpOpRzOjvxLFsMJJ41ZC3agwFibMaDumeAicMg/640?wx_fmt=png) 考虑到 GPT 不擅长数学计算，所以我接着让它写一段 Python 代码来实现快速计算，并检验上面回答的正确性。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5Fuoibz8dkNgsN44JcfjScetUiciaIXHF1rdDMcyLdFics5amT6r3oTSt7MXeYGQ/640?wx_fmt=png) 运用上面的 Python 代码，得到的结果确实是 0.9502，即 95.02%，验证了 ChatGPT 回答的正确性。  有了 Python 代码之后，我们还可以举一反三，修改事件发生的概率和独立试验的次数，这样就能快速计算不同条件下的概率分布。  为了更加清晰地展现泊松分布的变化，我们继续让

GPT 用 Python 绘制概率分布的曲线，稍加修改之后的代码如下：

    

          *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   *   * 

    

    

    

    import numpy as npimport matplotlib.pyplot as pltfrom scipy.special import factorial  

    # 设置中文显示字体plt.rcParams['font.sans-serif'] = ['SimHei']  

    # 定义泊松分布的概率质量函数def poisson_pmf(k, lamb):    return (lamb**k * np.exp(-lamb)) / factorial(k)  

    # 定义参数p = 0.0003  # 事件发生的概率n = 10000  # 独立试验的次数lamb = n * p  

    # 生成 x 坐标轴的取值范围x = np.arange(0, 11)  

    # 计算对应的泊松分布的概率质量函数值pmf = poisson_pmf(x, lamb)  

    # 放大图表plt.figure(figsize=(12, 6))  

    # 绘制概率分布曲线plt.plot(x, pmf)plt.xlabel('次数', fontdict={'fontsize': 16})plt.ylabel('概率', fontdict={'fontsize': 16})plt.title("进行 %d 次独立试验的概率分布" % n, fontdict={'fontsize': 20})plt.grid(True)  

    # 调整刻度数字的字体大小plt.xticks(fontsize=15)plt.yticks(fontsize=15)  

    plt.show() 

`  

`

修改其中的 n 值，运行得到不同的概率分布曲线，从图中可以看出，随着试验次数的增加，泊松分布曲线越来越接近于正态分布曲线。

![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibzdFgjOoOOqNaeibEDibRI7obeU7tmeiatAVJtwnsgonz5iciaFtuVz6xRXdw/640?wx_fmt=png) ![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibzAsVk6zibMNwpGT1yvI7FFaP3qmLSiaZUnKH1L9MAOkVe5HOTNED1oCng/640?wx_fmt=png) ![](https://mmbiz.qpic.cn/mmbiz_png/giaycic3UNwo3TBGx2aNBsRG6YEw5FuoibzMK3mlVFJzrAJ6GrfcTUIcegaLqdia2VcnVuOeSdtic0AOIa0U7mRTicWQ/640?wx_fmt=png) **泊松分布**

**特别适用于预测事件发生的概率。比如，通过对历史数据进行分析，我们可以预测某个时间段内到达某个地点的乘客数量，也可以检验某个机器的故障率是否符合预期，还可以估计某个地区在特定时间内发生车辆事故的概率，从而为保险费率的制定提供依据。**

## **最后的话**

在泊松分布出现之前，概率论与数理统计其实是两个互不相关的学科。概率论主要研究未发生的随机事件，也就是根据已知的模型和参数，预测未来的数据；而数理统计则主要是用来描述已经发生的现实。

自从泊松分布出现之后，概率论与数理统计产生了紧密的联系，这让统计学变得更加强大，我们可以根据已知的数据，去推测未知的世界，还原世界本来的样子，而且可以被验证。

很多人判定一件事发生的概率总是存在很大的误差，导致决策失误，损失惨重，其中一个重要的原因就是靠直觉，而不是靠严密的数学逻辑和推导。

通过学习和运用泊松分布，我们可以改变看待世界的方式，改变自己做决策的方式，甚至改变自己的心性，用更加理性的思维去解决问题。

比如，由于世界的不确定性和随机事件的存在，我们在准备资源时，只达到平均值是远远不够的，还需要准备一些冗余量。如果一个人忙得没有时间进行思考和休息，就难以摆脱「穷忙」的状态。

在《稀缺》这本书中，作者指出，当一个人处于稀缺的状态时，会产生很多危害，包括：认知能力下降、只关注眼前紧急的事、忽视真正重要的事、透支未来的资源、做出错误的决策、陷入恶性的循环等。

记住：凡事都要记得给自己留有余地，因为生活中难免会发生一些意外的随机事件。只有预留一定的机动时间，才能避免打乱正常的生活节奏，让自己的生活多一份从容。就好比在开车的时候，与前车保持一定的距离，这样才能更加安全地到达目的地。

**总之，** **泊松分布**

**是一种重要的概率分布模型，具有广泛的应用领域。通过学习和运用泊松分布，我们可以更好地理解和分析随机事件发生的规律，并用来预测未来发生的概率，进而帮助我们更好地用数据化解难题，让分析更加有效。**

延伸阅读：  《刘嘉概率论通识讲义》  《吴军数学通识讲义》

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)