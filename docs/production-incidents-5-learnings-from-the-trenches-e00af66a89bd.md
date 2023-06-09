# 生产事故:从战壕中学到的 5 点经验

> 原文：<https://medium.com/javarevisited/production-incidents-5-learnings-from-the-trenches-e00af66a89bd?source=collection_archive---------3----------------------->

![](img/e1af48d83a76fd21c0aca8cb2174ecb2.png)

比约恩·尼尔森在 [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral) 上拍摄的照片

*哦哦——生产警报响了，你在值班。肾上腺素激增，你冲到电脑前看看发生了什么——听起来很熟悉吧？我已经遇到过几次这种情况，我想分享一些我到目前为止学到的东西。*

# 针对高风险部署制定紧急回滚策略

所有部署都有不同程度的风险。有些是小的错误修复，有些是影响整个应用程序的主要数据库更改。事先想出一个过程来回滚这些更改并将系统返回到一致的状态是一个很好的练习。在事故期间，这将花费相当多的时间(因为每个人都很恐慌),并且一些选项可能不再可行，例如，如果您放弃了一个错误的表，并且您没有备份。

# 毫不犹豫地寻求第三方系统的支持

根据我的经验，大多数生产事件都是由最近的一次部署引起的；然而，有几次我们的第三方依赖者(例如云提供商)出现了问题。不要等到 200%确定故障出在您的应用程序之外，如果在检查了问题的所有潜在原因、相关日志和指标后，您至少 80%确定故障出在第三方系统，请致电他们的支持寻求帮助。最好的情况是他们会解决问题，最坏的情况是——你获得了有价值的知识，知道问题在别的地方。

了解您与这些第三方签订的服务级别协议(SLA)以及他们保证的支持请求响应时间也很有用。对于最关键的第三方集成，最好提供高级支持，以便能够快速解决关键问题，最大限度地减少对客户群的影响。

# 对客户透明并交流进展

如果某个事件需要超过 10-15 分钟才能修复，通知您的客户群可能是个好主意。这向您的客户表明，您已经意识到了这个问题，并且正在积极尝试解决它。可能他们甚至还不知道这个问题，但这将提升您公司的形象，向他们展示您正在努力观察您产品的健康状况。如果事件需要更长的时间来解决，请向您的客户群更新进度。

我发现顾客比我想象的要理解得多。

# 在事件解决过程中指定一个人来记录所有事情

调查更严重/令人困惑的事件通常意味着涉及越来越多的人。参与者将需要提高速度，在这种高压情况下，最好避免浪费宝贵的时间一遍又一遍地解释事情，甚至更糟——让人们做已经做过的事情。因此，一旦事故开始，任命一个人监督过程并记录以下信息(时间戳和结果！):

*   检查了什么(最近的部署、[日志](https://javarevisited.blogspot.com/2011/05/top-10-tips-on-logging-in-java.html)、指标等)；
*   尝试了什么(重新部署、流量调节等)；
*   谁在做什么？

该日志对于确定流程的哪些部分可以改进非常有价值，也可以在撰写事后分析时使用。

# 从事件中学习和改进

请事件的主要参与者对事件进行反思，然后安排一次会议，讨论在监控、响应、问题调查等方面可以改进的地方。可能会引入一些改进，以避免将来发生此类事件，或者最大限度地减少识别/修复问题所花费的时间。

最重要的是，记住生产事故是不可避免的——保持冷静，尽力而为，不要害怕寻求帮助。