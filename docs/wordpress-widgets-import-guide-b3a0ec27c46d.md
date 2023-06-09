# WordPress 小部件导入指南

> 原文：<https://medium.com/visualmodo/wordpress-widgets-import-guide-b3a0ec27c46d?source=collection_archive---------0----------------------->

有时，当移动 WordPress 站点时，你可能需要保存并在不同的 WordPress 安装之间重用小部件设置。如果一个站点只有几个小部件，那么你可以手动操作。但是，如果多个侧边栏和小部件区域中有许多小部件，那么您需要一个更好的解决方案。在本文中，我们将向您展示如何进行小部件导入

# WordPress 小部件导入

WordPress 小部件菜单(外观——小部件)是奇迹发生的地方。你可以挑选、选择和定制任何部件来美化你的博客的边栏和页脚。一旦你完美地选择和设置了这些——这可能要花很长时间——你就不想再做一次了。尤其是如果你使用了大量的定制代码片段或者其他需要反复复制粘贴的东西。

![](img/0a22704e0f3cacba0aa0c158afd379f8.png)

# 准备好了吗

一旦你有了这个完美的插件，去 WordPress.org 插件库给自己找一个叫做*Widget Importer&Exporter*的插件。显然安装它并激活它。

现在，您将在工具中有一个新的菜单项— [小部件](https://visualmodo.com/)进口商&出口商。你可以在仪表盘侧边栏或者*安装的插件*页面访问它。不管怎样，当你到达那里时，你会看到这个插件做得最好的两件事的按钮:*导入部件*和*导出部件。除此之外，插件没有其他设置。只需点击并运行。*

现在，需要注意的重要部分是，在*导出小部件*(上面的#2)下，插件声明它将为所有活动的小部件*创建一个导出文件。*这意味着只有当前显示在侧边栏、页脚或另一个 widgets 化区域中的小部件才会被导出。因此，您不必处理 20 个您可能不使用的默认小部件的空白副本。

点击*导出小部件*按钮将生成一个*。wie* 文件为你的网址，你可以保存在任何你想要的地方。

*。wie* filetype 仅用于此插件。但是，通过在代码编辑器中打开文件，您可以很容易地看到它是如何导出数据的。WordPress 将小部件数据作为序列化数组保存在数据库中，所以这就是你在这里看到的。从技术上讲，您可以使用 SQL 手动查找和移动这些内容，但我怀疑您是否愿意这样做。

# 导入流程

然而，导入文件稍微复杂一点(但不会太复杂)。你也需要访问任何一个你正在传输部件的 WordPress 站点。不仅是访问，你还需要安装和激活插件的许可，因为你必须在第二个站点上安装*插件导入器&导出器* [插件](https://wordpress.org/plugins/widget-importer-exporter/)。

旁注:注意到管理[仪表板](https://visualmodo.com/blog/)使用的不同颜色了吗？这个选项可以在你的用户档案中更改，当处理多个 WordPress 安装时使用不同的配色方案是一个非常好的主意。这有助于将他们分开。像这样在两个不同的装置之间传输数据简直是奇迹。试试看。

安装并激活后，只需点击小部件*导入/导出*链接或转到工具-小部件导入器&导出器选项卡。找到*。wie* 文件，无论你把它保存在你的硬盘或服务器上。准备就绪后，您只需点击*导入小部件*即可启动该过程。

紧接着，插件会将您重定向到结果摘要。如果一切顺利(很可能是这样)，您将看到绿色的 *imported* 消息，表明您成功了。

当你检查你的外观——微件屏幕时，你会看到满眼的成功。你所有的区域和部件都和你在最初的站点时一样。

完美无缺。导入完成后，小部件就开始运行。就像他们说的一样简单。

# 复制小部件

虽然您可以手动创建 widget 的副本，但是如果您尝试两次导入同一个 widget，您将无法这样做。将显示橙色文本的*小部件已存在*消息，而不是绿色的成功消息。这样，您就不必担心导入刚刚导出的相同小部件，并实时推送所有内容的副本。(记住，这也是通过改变仪表板颜色来保护的。)

# 现有小部件

你已经安装在网站上的小工具也是安全的。无论何时你使用这个插件导入任何东西，新的插件都会被简单地添加到 widgetized 化的区域。而不是覆盖您现有的设置。因此，只要你已经做了一些清理工作，这样你的侧边栏*等*就不会超出它们的界限，你可能在导入阶段之后几乎没有什么工作要做。

# 部分

因为数据存储在*内的数组中。wie* 文件，没有解释的余地。该插件寻找一个名为侧边栏的窗口小部件区域，将所有侧边栏的窗口小部件放入其中。页脚区#1 也是如此，依此类推。但是如果你只有页脚 A，它不知道该怎么办。没有 1:1 的匹配。并且数组不能从语义上将该标题解释为功能上相同的东西。

因此，它把任何它在你的*非活动窗口小部件*区域找不到位置的东西放在外观——窗口小部件下面。这是您放置想要保存其设置，但不想在您的站点上显示的微件的位置。因此，您维护了导入本身的完整性，但是您确实需要手动将它们放置到位。不过，没有数据丢失。

# 结论

看到了吗？从一个网站向另一个网站转移[小工具是一个真正无痛、简单的过程。点击几下就搞定了。如果您要使用相同的主题访问一个全新的站点(并且没有定制任何小部件区域名称)，您可以在几分钟内完成。你很久以前就做了这项工作，在第一个站点就把一切都做得恰到好处，所以为什么要重新发明轮子呢？只需将数据库数组导出为一个*。wie* 把它扔进新的网站，你就可以继续你*还没有完成的工作。*](https://visualmodo.com/wordpress-themes/)