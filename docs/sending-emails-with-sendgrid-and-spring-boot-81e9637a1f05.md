# 使用 SendGrid 和 spring boot 发送电子邮件

> 原文：<https://medium.com/javarevisited/sending-emails-with-sendgrid-and-spring-boot-81e9637a1f05?source=collection_archive---------1----------------------->

![](img/f6f2a8b93599d45c24592cd954e4014d.png)

# 什么是 SendGrid？

SendGrid 是一个基于云的 SMTP 提供商，允许你发送电子邮件，而不必维护电子邮件服务器。 **SendGrid** 管理所有的技术细节，从扩展基础设施到 ISP 拓展和信誉监控到白名单服务和实时分析。

# 创建帐户:

  

然后登录您的帐户:

![](img/0b49522eb1f4ebff21b68cfff38563d1.png)

你会看到这样的东西。

# 创建弹簧启动应用程序:

【https://start.spring.io/ 

依赖项:Spring Web 和 Spring Boot 开发工具。

![](img/b663121ec5a473508e79ecc85f292169.png)

下载并解压缩项目后，添加这个依赖项:

```
<dependency><groupId>com.sendgrid</groupId><artifactId>sendgrid-java</artifactId><version>4.0.1</version></dependency>
```

请参见下面的 pom.xml:

# 创建单一发件人验证:

导航到[https://app.sendgrid.com/settings/sender_auth/senders](https://app.sendgrid.com/settings/sender_auth/senders):

![](img/3514c726ee028911044064e674c8d823.png)![](img/e90620bbd84a71df786cdf8ff720ceee.png)

填写完所有输入后，点击创建按钮。然后你会收到一封激活邮件。

# 发送电子邮件:

## 1.获取 API 密钥:

![](img/dd2e48a4310623244c67d1a00f2bca72.png)

在控制面板中，单击电子邮件 API，然后单击集成指南。

![](img/81c90efd72f27df858deeb1e65ae5973.png)![](img/17228320046f22fdffb29b346ae0f366.png)

选择了 Web API

![](img/f2b0757858c3a1347f9a3081d5499a40.png)

然后是 java:

![](img/5a855187c7fd7c2e9733269445c19b20.png)

输入密钥名，然后单击创建按钮

![](img/8c48821ee90f5c45059edf9c2a93f589.png)

复制您的 API 密钥。

## 2.创建服务:

## 3.创建静止控制器:

## 4.测试 API:

论邮递员

post:[http://localhost:8080/API/send-text](http://localhost:8888/api/send-text)

您将收到一封电子邮件，确认您的垃圾邮件。

# 发送带有动态模板的电子邮件:

SendGrid 使我们能够使用模板或创建自己的模板。

## 1.让我们创建一个模板:

导航[此处](https://mc.sendgrid.com/dynamic-templates)

![](img/92f84618821275a854117b2a67a419b9.png)![](img/d8c3901fd26b39b7a228dc5c110ba735.png)![](img/fba3f2b82d35db811b1b04e1b02fb366.png)![](img/3585434e95ea1c6a7fb08506c5be8557.png)

点击 SendGrid 电子邮件设计，我们将选择一个预建的。

我选择脱离电网冒险。

![](img/2609269e555ebdf2b2436c5f95b3f85c.png)

然后选择设计编辑器

![](img/162fa0c05cee8e49a42560549bd02563.png)

现在让我们给模板添加一些修改。

单击欢迎加入家庭，并将文本更改为

欢迎{ {名字}}

**{{first_name}}** 表示它是一个变量，将使用代码动态更改。

![](img/5139339e2b68311c81505cce5e6af1e2.png)

单击预览查看输出

![](img/66274ef5e1bdfe2c2ce0b7af9efab913.png)

单击显示测试数据

![](img/5ac58b5ddd987a26c43c819927726af3.png)

模板已动态更改。

现在点击保存按钮，然后返回箭头

![](img/ad647520157535822d63fa407064bad9.png)![](img/bc5eb85026900ce655c2b07ef5e562db.png)

复制模板 id。

## 2.更新邮件服务:

## 3.更新 rest 控制器:

```
@PostMapping("/send")public String sendWithTemplate() throws IOException {return mailService.send();}
```

## 4.测试新的 API:

论邮递员

post:[http://localhost:8080/API/send](http://localhost:8888/api/send-text)

您将收到一封带有我们模板的电子邮件。

验证您的垃圾邮件。

# 最后一句话:

您可以在这里找到源代码:

  

**如果你喜欢这篇文章，请鼓掌**👏**分享它，让其他人也能找到它！关注我，了解我更多信息**😄。