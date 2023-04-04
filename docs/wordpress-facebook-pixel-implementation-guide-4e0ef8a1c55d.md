# 脸书像素实现指南

> 原文：<https://medium.com/visualmodo/wordpress-facebook-pixel-implementation-guide-4e0ef8a1c55d?source=collection_archive---------0----------------------->

你在考虑重新定位脸书的广告吗？你想在 WordPress 安装脸书像素再营销/再定位吗？在这篇文章中，我们将向你展示如何在 WordPress 中安装脸书再营销/再定位像素。

简而言之，脸书像素就像脸书广告的谷歌分析。它可以让你更好地定位广告，并看到它们在将点击转化为销售方面的有效性。

但是如果你不是超级科技通，实际上弄清楚如何让脸书 Pixel 在 WordPress 上运行会有点困难，对吗？

为了帮助你，我将给你一个初学者友好的教程，介绍两种不同的方法:

*   **带手动代码** —这是一个轻量级选项，可以帮助你添加脸书像素代码，除此之外别无其他。
*   **带插件**——这种方法的优点是你可以从你的 WordPress 仪表盘内部创建[自定义受众](https://developers.facebook.com/docs/facebook-pixel/pixel-with-ads/website-custom-audiences)和转换目标。这个插件特别适合电子商务商店，因为它有专门的 WooCommerce 和简单的数字下载集成。

如果你计划使用自定义受众和转化目标，我建议你使用插件方法。但是如果你只是想使用脸书像素来创建[长相相似的观众](https://revive.social/use-facebook-advertising-campaigns-to-boost-your-business/)和其他更基本的功能，手动代码实现是满足你需求的最简单的解决方案。

# 脸书像素到 WordPress 手动

![](img/aa0dd0458872972280e7f1b94aedf9f1.png)

要手动添加脸书像素到 WordPress，你必须完成两个步骤:

*   在脸书网站创建一个新的脸书像素(如果你还没有)
*   将脸书像素的跟踪代码插入到你的 WordPress 站点的部分

这没什么太复杂的——我保证！让我们开始吧…

# 像素创建

要开始，请到脸书广告管理器的**像素**标签。你可以点击这个链接直接去那里。如果你还没有创建一个像素(*你只能为每个账户*创建一个像素)，你可以点击绿色按钮**创建一个像素**:会出现一个对话框，询问你的名字——然后你需要做的就是点击**创建**。

之后，你应该会看到一些选项，如何添加脸书像素到您的网站。选择**自己手动安装代码**选项:

这应该会显示脸书像素跟踪代码:把这段代码放在手边，因为在下一步中你会用到它。

# 跟踪代码

![](img/f65fda9664ceb67e5ce5834afdf7a21d.png)

虽然有很多不同的方法可以将这样的代码片段添加到 WordPress，但我认为最简单的方法是一个名为 Insert Headers and Footers 的免费插件:

# [插入页眉和页脚](https://wordpress.org/plugins/insert-headers-and-footers/)

以下是如何做到这一点:

*   安装并激活免费插入页眉和页脚插件
*   进入**设置→插入页眉和页脚**
*   将脸书像素跟踪代码粘贴到标题框中的**脚本中**
*   保存您的更改

就是这样！你刚刚学习了如何将脸书像素添加到 WordPress。在本文的最后，我将向你展示如何测试你的新脸书像素是否工作正常。但是首先，让我快速介绍一下插件方法。

# 像素咖啡因 WordPress 插件

Pixel Caffeine 是来自 AdEspresso 的免费插件，这是一款流行的脸书广告管理工具。

与上述方法相比，使用 Pixel Caffeine 的优势在于您可以:

*   从你的 WordPress 仪表盘上创建基于 WordPress 相关操作的自定义受众。
*   为 WooCommerce 制作脸书动态广告，假设你使用的是 WooCommerce 商店。
*   轻松跟踪转换，包括 WooCommerce 的专用集成和轻松的数字下载。

如果你使用 WordPress 来驱动一个电子商务商店，这个功能特别有用。但是，即使你只是运行一个普通的网站，自定义受众功能可以帮助更先进的脸书广告商。

在你可以使用这个插件之前，你需要已经在脸书广告管理器中创建了一个脸书像素(*如果你需要帮助*，你可以按照我在上一节的步骤 1 中概述的说明进行操作)。

# 设置像素咖啡因

要使用 Pixel Caffeine 插件，像安装和激活其他插件一样安装和激活它。

# [像素咖啡因](https://wordpress.org/plugins/pixel-caffeine/)

然后:

*   转到你的 WordPress dashboard 侧边栏中新的**像素咖啡因**区域
*   转到**通用设置**选项卡
*   点击 **FACEBOOK CONNECT** 按钮(如果你想要所有的额外功能，这是必要的)

一旦你点击那个按钮，你会看到一个提示说“ **Pixel Caffeine** 想要管理你的业务”。点击**确定**:然后，你会被带回你的 WordPress 仪表盘，在那里你可以选择你的**广告账户**和**像素 ID** :就这样！您的 Pixel 现已启动并运行。

要利用 Pixel Caffeine 的更多高级功能，您可以使用**自定义受众**和**转换/** [**事件**](https://visualmodo.com/) 的选项卡:

# 仔细讨论

在你把像素添加到 WordPress 之后，你还需要做一件事:确保脸书像素确实在工作！

为此，你安装了[脸书像素助手 Chrome 扩展](https://chrome.google.com/webstore/detail/facebook-pixel-helper/fdgfkebogiimcoedlicjlajpkdmockpc?hl=en)。一旦你激活了 Chrome 扩展，访问你安装脸书像素的网站。如果您的 Pixel 正在工作，当您单击扩展时，您应该会看到类似这样的内容:

这就对了。这就是将脸书像素添加到 WordPress 所需要做的全部工作。享受您的再营销、[转换](https://visualmodo.com/wordpress-themes/)跟踪和自定义受众！关于在脸书上宣传你的 WordPress 网站，你还有什么需要我们解释的吗？请在评论中告诉我们！