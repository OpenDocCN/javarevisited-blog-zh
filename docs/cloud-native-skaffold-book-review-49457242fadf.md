# 使用 Skaffold 轻松开发云原生应用——书评

> 原文：<https://medium.com/javarevisited/cloud-native-skaffold-book-review-49457242fadf?source=collection_archive---------3----------------------->

![](img/cde19ee98231b191b11ac82cbb3fa2ef.png)

我是一个非常关心生产的开发人员。但我不是德沃普家的人，不幸的是我很不擅长这个。这就是为什么当我听说 Skaffold 时，它立即激起了我的兴趣。写 Kubernetes 云原生应用没有嗯…写 Kubernetes 原生应用…给我报名！

不幸的是，众所周知。学习一项新技术的时间是当我们确实需要它的时候，然后我们急着要把它拿出来。我们中很少有人有时间从繁忙的一天中抽出来研究一些东西和学习一些新的东西。这就是为什么当《**使用 ska fold**轻松开发云原生应用》一书的作者 [Ashish Choudhary](https://twitter.com/iASHeeesh) 在 [foojay.io](https://foojay.io/) slack 小组中征求评论者时，我抓住了这个机会。我可以学到一些有趣的东西，并富有成效(本书评)。

在我们继续书评之前，我想先弄清楚以下几件事:

*   我个人并不认识阿什什·乔杜里
*   我没有收到任何评论，也没有提供任何附属链接或类似的东西。[这是本帖中唯一一个指向本书](https://www.packtpub.com/product/effortless-cloud-native-apps-development-using-skaffold/9781801077118)的链接，它没有会员代码！
*   我过去为 publisher Packt 做过一些工作(一个在线课程)——我认为这不会影响我在这里的判断。我已经有一段时间没做那项工作了

另一个重要的细节:我没有运行代码或者浏览样本。我刚刚读了这本书。我也做得比较快，用的是 PDF 版本。因此，我觉得我失去了书中的一些核心经验。

# 斯卡福德是什么

ska fold 是一个开源项目，由一名谷歌工程师在遭受了云原生 Kubernetes 部署的痛苦之后开始的。它实际上是一个命令行工具，可以自动化 Kubernetes 应用程序的构建、推送和部署步骤。

仅此一点就足以证明一份信息表。周边系统集成了 Maven/Gradle/Spring 等。创造流畅的开发体验。这使得在本地构建/调试 Kubernetes 应用程序几乎和运行常规的 Spring Boot 应用程序一样简单。

显然会有额外的复杂性和配置，但核心思想是相同的。开发者仍然需要理解 Kubernetes 的基本思想，这是没有办法的。但是你可以消除一些相关的麻烦。Kubernetes 针对的是 devops，它的很多特性对于开发者来说都是多余的。通过这种方式，我们可以轻松构建云原生微服务。

# 这本书

Packt 书籍提供了对当前技术的快速而实用的介绍。它们的优势在于包含了许多其他书籍可能遗漏的当前细节。然而，当你需要这本书的时候，这些细节可能已经过时了。这是你需要根据你的出版经验做出的权衡。

由于主题‌is 是一个非常具体的工具，我看到了进入具体细节和样本的价值。

乔杜里将这本书分为三个部分:

1.  库伯内特人的噩梦——斯卡福德来拯救
2.  斯卡福德入门
3.  使用 Skaffold 构建和部署云原生 Spring Boot 应用

在第一部分中，我们通过诸如“使用 Kubernetes 开发云原生应用程序——开发人员的噩梦”等章节，对构建 Kubernetes 应用程序的“问题”进行了一瞥。

乔杜里在第二部分介绍了斯卡福德。第三部分讨论了部署、替代方案等细节。

## 云原生

这本书关注于开发周期的内/外循环的分离。内环是本地开发环境，外环是生产/CI/CD 环境。使这种开发风格“云原生”的是内外循环之间的相似性。

在 CI 周期的集成测试中，以及最终通过 GitOps 等工具推向生产的过程中，也有类似的关注点。酷的是，我们在开发的所有阶段都使用非常接近生产的环境。

Skaffold 成为云的另一个特性是通过 jib 的即时部署。因此，当我们在 IDE 中保存更改时，我们可以立即看到本地 Kubernetes 环境中的更改。这很酷，仅此一点就值回 Skaffold 的门票钱(当然是免费的)。

# 我喜欢什么

## 写作和专注

Choudhary 是一位才华横溢的作家，他使用清晰的语言和例子。这些例子并不太冗长，有时这类书就是如此。他写了一本针对 Kotlin/Java 开发人员的书，非常棒。

Skaffold 的核心思想和好处在书的早期就已经介绍过了，而且非常明显。有几个图表说明了大的设置件。

## 客观性

这本书涵盖了斯卡福德的竞争对手，似乎对它的处理相当客观。这是在书的结尾，所以如果你对斯卡福德有疑问，我建议你先看结尾。

## 出版

虽然有点浪费(稍后会有更多介绍)，但 Packt books 的布局和往常一样非常棒。Packt 书籍有很好的布局、目录和索引。这使得读取/引用过程更加顺畅。

# 我不喜欢的是

## 云原生

我感觉云原生这个词是 GraalVM 和框架如 [Quarkus](/javarevisited/10-best-free-dropwizard-vert-x-micronaut-and-quarkus-online-courses-for-java-developers-9c2b4161f17) 的‌co-opted。我理解乔杜里的目的，并认为这对这本书来说是有意义的。但这是那些过度使用的短语之一，失去了一些意义。一个[云本地书](/hackernoon/top-5-spring-boot-and-spring-cloud-books-for-java-developers-75df155dcedc?source=---------23------------------)是一个非常模糊的说法，Skaffold 缩小了范围，但只有在你知道那是什么意思之后。

因为这个原因，我跳过了整整一章关于 GKE 的内容。这与我无关。

## 出版

虽然我喜欢 Packt 书籍，但我有两个不满。我希望他们在这些方面有所改进:

*   我不喜欢书里的填充物。这本书可能会少 100 页，这是由于空白页、大页边空白、间距过大等原因造成的。想想树的包装(其他出版商也有！).
*   我希望其他出版商会拿起曼宁的源注释风格。这很难做到，因为[我发现](/sketch-app-sources/using-sketch-and-asciidoc-to-generate-a-professional-tech-book-ef5b5d8dd410)，但可读性是如此之好…

请注意，这两个评论并不是 Packt 独有的，而是适用于大多数出版商。

# 一锤定音

我喜欢这本书。不过，我对斯卡福德还没拿定主意。作为云原生领域的后来者，我觉得我需要跳过一些麻烦。这使得它很有吸引力。但是由于过去的创伤，我试图远离谷歌服务。斯卡福德不需要 GCP，没有它也很有用，所以我打算尝试一下。

我喜欢 Choudhary 把这本书的重点放在 Java/Kotlin 上，因为我是一个 Java 迷。但是我最近做了很多云本地的多语言工作，这可能是一个限制。我在 NodeJS 调试的书上看到有提到，但也就这样了。老实说，我不知道是否可以用 Skaffold 来做我的多语言演示。那样会很酷。

我认为这不是因为 Skaffold 的局限性，而是因为书中的遗漏。