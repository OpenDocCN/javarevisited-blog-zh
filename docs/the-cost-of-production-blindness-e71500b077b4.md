# 生产盲目的代价

> 原文：<https://medium.com/javarevisited/the-cost-of-production-blindness-e71500b077b4?source=collection_archive---------4----------------------->

![](img/d4e6c6b9cd07344f19f3557ce8b833fd.png)

当我在会议上发言时，我经常回想起几十年前我们通过踢服务器来观察生产的事实。这显然不再实用。我们看不到我们的产品。这是一种我们无法触摸或感觉的无定形的云。一种我们读到过但没有完全掌握的力量。

在这种情况下，我们有物理证据表明云是存在的。

我们行业这一重大转变的一部分是我们作为工程师的基本角色的改变。德沃普斯和 [SRE](/javarevisited/13-best-courses-to-learn-devops-for-senior-developers-in-2020-a2997ff7c33c) 是当时不存在的角色。然而今天，它们对于大型企业来说往往是必不可少的。他们带来了生产可靠性的巨大进步，但也带来了成本:距离。

生产是在无定形的云中进行的，这是随处可得的。然而，它从未远离过为它编写软件的人。我们不再拥有十多年前认为理所当然的基本洞察力。

# 有那么糟糕吗？

是，也不是。我们放弃了一些洞察力和控制力，却得到了很多回报:

*   稳定性
*   简单
*   安全性

这些都是非常难以置信的好处。我们不想放弃这些好处。但是我们也失去了一些洞察力，调试变得更加困难，复杂性也增加了。我们之前讨论过这些问题，但今天我只想谈一个影响…

# 费用

这是一种失明。

我写了很多关于这种情况对我们云部署可靠性的影响。但是今天我想谈谈财政和环境成本。最初，云被宣传为节约成本的措施，这是有一定道理的。部署的灵活性让我们能够削减硬件成本，进行整合和简化。

但是随着我们习惯了[云](/javarevisited/5-best-google-cloud-digital-leader-certification-courses-for-beginners-5d8f25d587)，我们对规模/可靠性的胃口越来越大。我们最终将部署简化到这样的程度，启动容器可以无缝地完成，不需要我们进行交互。这是巨大的进步，但也令人不安。我们慢慢失去了对成本的控制，最终以少花钱多办事而告终。

那么解决办法是什么呢？

杀伤人员地雷是专门围绕这一问题而凸显出来的一个类别。今天，它们比以往任何时候都更加重要。它们帮助我们了解帕累托原则(80/20 法则)，这样我们就可以将优化集中在成本最高的特定领域。

这是 DevOps 每天使用的强大而重要的工具，但也是非常有限的。

在我们继续之前，我想花点时间讨论一下成本的概念。最明显的影响是我们每月的云提供商账单。这项工作可能会资助一个部门。但是以我的拙见，还有一个更重要的成本:环境成本。我们倾向于忽略电力支出，因为它是一种非常不确定的支出。但这种成本是巨大的，例如，一年内一个云实例的成本可能相当于一次跨大西洋飞行。

我们看不到底层的硬件，但它确实存在，而且它带有碳足迹。通过优化，我们可以显著影响这两种成本。

# 有效观察生产

APM 非常适合在高水平上衡量绩效。但是它们很少提供应用程序动态内部工作的细节，以及我们可以在内部采取的成本削减措施。我经常把它们比作蝙蝠信号或检查引擎灯。他们通知我们一个问题，但是却没有工具让我们检查细节。

这就是[开发人员可观察性工具](https://lightrun.com/)可以填补空白的地方。这些工具可以提供对应用程序的低级应用洞察。验证假设，并为开发人员提供充分理解生产的方法。

不讨论理论，让我们给出一些例子，你可以用开发人员可观察性工具来降低你的生产成本。

# 减少日志

日志接收可能是应用程序中开销最大的特性。删除一行日志代码最终可以节省数千美元的接收和存储成本。我们倾向于写得太长，因为另一种选择是生产问题，我们无法追溯到其根本原因。

我们需要一个中间立场。我们希望能够在不过度记录的情况下跟踪一个问题。Developer observability 允许您根据需要将日志动态添加到生产中。这将你从过度记录的需要中解放出来，让你专注于记录合理的数量。您还可以提高日志级别来保持日志记录。我在这里写了关于这个问题的深度[。](https://lightrun.com/best-practices/logging-best-practices-mdc-ingestion-and-scale/)

# 贮藏

我对性能的三大建议一直是:

1.  贮藏
2.  贮藏
3.  贮藏

真的没别的了。一切都归结于此。不幸的是，众所周知，缓存未命中很难调整和检测。在生产中，这是一个更大的问题，我们需要考虑不断变化的环境。例如，我们在社交网络上缓存用户的 10 个朋友，但在生产中，成长团队鼓励友谊，用户有更多的朋友…

你会有更多的缓存未命中，你甚至不知道。

在缓存未命中上放置[条件断点](https://javarevisited.blogspot.com/2011/07/java-debugging-tutorial-example-tips.html)或临时条件日志，并检查它们，可以大大有助于检测类似这样的微妙问题。如果处理得当，这可以对性能产生数量级的影响。

然而，这里有一个更大的支出。许多开发人员完全忽略了 L2 缓存。这可以理解。它们很难维护和调试。尤其是在生产方面。一次缓存损坏或一个值不同步，就会导致严重的错误。问题是在生产环境中调试这些东西是必不可少的。由于缓存的分布式本质，它在生产中的行为完全不同。

我们构建了开发人员可观察性解决方案来调试这些确切类型的问题。通过将快照和日志置于缓存填充/失效之上，我们可以缩小损坏点并修复缓存关系问题。通过将这些解决方案部署到您的生产服务器，可以显著降低开销！

# 微观基准

APM 为我们提供了高水平的性能数据和总体方向。他们没有提供我们需要解决的代码行。那是留给我们猜测的。如果系统在本地运行时表现一致，这应该没问题。不幸的是，这种情况很少发生。例如，一个[数据库查询](https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html)在生产环境中运行时会产生明显不同的影响。根据本地分析结果，您可能会在错误的优化上浪费精力。

开发人员可观察性工具提供了缩小代码片段性能开销的能力。这让我们可以跟踪 web 服务堆栈，缩小占用 CPU 时间最多的实际行的范围。我们可以通过添加 tictoc 度量来实现这一点，该度量测量 tic 线和 toc 线之间的时间。

我们可以标记一个代码块，并获得关于其执行时间的统计数据。正如在生产中特定查询花费更长时间的常见情况一样，使用这个工具，我们可以很快证明这是性能问题的原因。像这样的许多“小”问题的影响在大型系统中可能是显著的，并且很容易意味着伸缩和瓶颈的区别。

# 验证和死代码

一个常见的问题是资源利用不足。杀伤人员地雷暴露了其中的一些问题，但没有全部暴露。当我们有死代码时，它对我们的底线的影响是显著的。

有多少次你[重构代码](/javarevisited/7-best-courses-to-learn-refactoring-and-clean-coding-in-java-47bea3c67006)或者因为不想碰的遗留问题而停止重构？

是的，遗留的混乱被用在你的代码中，所以你不想“冒这个险”。如果您最终更改了代码，您需要小心翼翼，整个操作可能要多花一个数量级的时间。这映射到成本，因为我们的时间是宝贵的，你可以用它来优化。大多数时候，它还会阻止一些主要的优化。

但是如果这个代码块没有被生产中的任何人使用呢？

如果用的人很少怎么办？

这正是计数器的作用。它计算到达一行的次数。它能告诉我们哪些方法对我们很重要，以及达到这些方法的频率。如果只有三个人到达那一行代码，你就不会那么担心重构了…

# 最后

我可以继续讨论这些技术，但是要点很简单:我们需要“看到”正在发生什么。作为开发人员，我们被赋予了构建产品的任务。但是让我们窥视生产的工具不如我们本地的工具有能力。我们从生产中得到的结果可能会非常误导人。

当我们扩展生产部署时，我们需要使用一类新的工具来以这种方式公开我们的代码。我可以用一个词来给现代生产分类:

**恐惧**。

当我们在生产中推动重大变革时，我们都会感受到这种根深蒂固的恐惧。人们因为把不好的东西推向生产而失去工作。太吓人了！

面对这样的恐惧，我们该怎么办？

我们继续前进，但要小心。我们步步为营，不冒大风险。我们的代码浪费吗？

也许吧，但是降低产量的风险比削减公司开支的好处要可怕得多。

开发者的可观察性是黑暗中的光明。当你在黑暗中点亮一盏灯时，你就带走了一些恐惧，让生产变得更加触手可及。我们可以测量、测试和快速移动。我们也对即将到来的变化所带来的风险有了更好的认识。工具也给了我们一种上升的感觉。我们能省多少钱？想象一下，在云计算方面节省整个部门的成本。这就是工作保障……这是对抗对危险变化的恐惧的最好方法。