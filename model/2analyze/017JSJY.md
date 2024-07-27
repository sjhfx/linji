运用概率思维，我们可以检验假设的合理性。

下面介绍的**假设检验模型** ，能帮我们更好地验证想法。

## **1. 模型介绍**

假设检验，按照字面意思来理解，就是先提出一个假设，然后再检验这个假设。

假设检验通常包括以下 3 个步骤：

**（1）提出假设**

根据实际情况，先提出一个假设，通常称之为 **零假设** ，用 H0 表示。

与 H0 对立的假设，通常称之为 **备择假设** ，用 H1 表示。

先假设 H0 成立，如果有足够的证据证明 H0 不成立，则拒绝 H0，接受 H1。

**（2）统计检验**

先确定检验的标准，在很多情况下，检验的标准是概率小于 5%，其中 5% 称为显著性水平，这个过程也被称为显著性检验。

根据假设的特征，选择合适的方法，统计检验的结果，计算拒绝 H0 的概率 P 值。

需要注意的是，一般应该在计算概率 P 值之前，先确定好检验的标准，以减少人为主观判断的影响。

**（3）做出判断**

根据统计的结果，按照检验的标准，决定是否接受原假设。

做判断的时候，要避免犯两类错误。

第一类错误是 **拒真** 错误，即错误地拒绝了零假设。

比如说，被告方本来无罪，但是虚假的证据让法官产生误判，导致错杀好人。

再比如说，一个人本来没有感染病毒，但是检查结果却错误地显示为阳性，简称为假阳性。

第二类错误是 **纳伪** 错误，即错误地接纳了零假设。

比如说，被告方本来有罪，但是因为证据不足让法官产生误判，导致放过坏人。

再比如说，一个人本来感染了病毒，但是检查结果却错误地显示为阴性，简称为假阴性。

当样本的大小固定时，犯两类错误的概率此消彼长，不可能同时减小。

因此，统计学家提出一个原则：在控制第一类错误的条件下，尽量减小犯第二类错误的概率。

也就是说，不轻易否定零假设，如果检验结果否定了零假设，那么说明否定的理由是足够充分的。

在实际解决问题的过程中，为了对某一假设取得强有力的支持，通常把这种假设本身作为备择假设 H1，而将这种假设的反面作为零假设 H0。

比如说，法官在审理案件的时候，首先会假设被告方无罪，然后根据指控方提供的证据，试着推翻一开始无罪的假设，从而接受与之相反的结论，即被告方有罪。

## **2. 应用举例**

假设检验模型广泛应用于许多领域，包括现代医学、心理学、经济学、社会学、计算机科学等等。

下面以《女士品茶》书中的一个故事为例，说明假设检验的过程。

在一个夏日的午后，英国剑桥的一群大学老师，和他们的妻子一起喝下午茶。

其中有一位女士坚持认为：把茶倒进牛奶里，和将牛奶倒进茶里，味道是不同的。

有一个人站出来  说：  让我们用科学的方法，来检验一下吧。

**（1）提出假设**

为了对这位女士的话取得强有力的支持，我们假设：

这位女士不能品尝出不同奶茶的区别。

**（2）统计检验**

先确定显著性水平为 5%，然后给这位女士随机喝 6 杯奶茶，让她分别说出：到底是茶倒进牛奶里？还是牛奶倒进茶里？

统计这位女士 6 次品茶的结果，发现她每次品茶的结果都正确。

如果她完全是靠乱猜的话，那么 6 次都猜对的概率是 50% 的 6 次方，大约等于 1.56%。

**（3）做出判断**

按照显著性水平为 5% 的检验标准，因为 1.56% 小于 5%，所以无法接受原来的假设，只能接受相反的结论。

也就是说，我们可以认为：这位女士确实能够品尝出不同奶茶的区别。

## 

**最后的话**

没有经过验证的想法，都是空想。

假设检验其实是一种基于概率的反证法。

为什么要用反证法呢？

以女士品茶的故事为例，如果是从正面来证明，喝 100 杯奶茶，要正确品出 95 杯以上才行，这样难度太大。

假设检验的基本思想，是在不确定性的条件下，相信小概率事件不会经常发生，如果真的发生了，那么就选择拒绝原来的假设。

假设检验并非绝对可靠，但是通过弄清楚最有可能的解释，我们可以更好地认识世界上的许多现象，从而得出更有价值的分析结论。

更新：2024-07-18

![](https://visitor-badge.laobi.icu/badge?page_id=sjhfx.linji&left_text=PageViews&right_color=%2300589F)