# 优化 WordPress 机器人。Txt 文件

> 原文：<https://medium.com/visualmodo/optimizing-wordpress-robots-txt-file-757c78399523?source=collection_archive---------0----------------------->

你听说过 Robots.txt 文件吗？如果你熟悉 WordPress，那么你可能知道 Robots 文件。它对你网站的 SEO 性能有着至关重要的影响。一个优化良好的 Robots 文件可以提高你的网站在搜索引擎中的排名。另一方面，一个错误配置的 Robots.txt 文件会严重影响你网站的 SEO。

![](img/b83fc0ef0666c79116e4bb95649fae86.png)

WordPress 会自动为你的网站生成一个 Robots.txt 文件。但是，您仍然需要采取一些措施来适当地优化它。SEO 还有那么多其他因素，但是这个文件是不可避免的。由于它的编辑涉及到使用一些代码，大多数网站所有者都不愿意对其进行修改。你不需要担心。今天的文章涵盖了它的重要性以及如何优化 WordPress robots 文件以获得更好的 SEO。在继续之前，让我们学习一些基本的东西。

# Robots.txt 文件是什么？

Robots.txt 是网站管理员创建的文本文件，用于指导网络机器人(通常是搜索引擎机器人)如何在其网站上抓取页面。此外，robots.txt 文件是 robots exclusion protocol (REP)的一部分，这是一组 web 标准，用于规范 robots 如何在 web 上爬行、访问和索引内容，以及如何将内容提供给用户。REP 还包括 meta robots 之类的指令，以及搜索引擎应该如何处理链接的页面、子目录或站点范围的指令(例如“follow”或“nofollow”)。

# WordPress 用法中的 Robots.txt

我已经说过，每个 WordPress 站点在根目录中都有一个默认的 robots.txt 文件。你可以去 http://yourdomain.com/robots.txt.查看你的 robots.txt 文件，例如，你可以在 https://visualmodo.com/robots.txt 查看我们的 robots.txt 文件

如果你没有 robots 文件，你必须创建一个。这很容易做到。只需要在你的电脑里创建一个文本文件，保存为. txt，最后上传到你的根目录。您可以通过 FTP 管理器或 cPanel 文件管理器[上传。](https://visualmodo.com/upload-wordpress-files-ftp/)

现在让我们看看如何编辑您的？txt 文件。您可以使用 FTP 管理器或 cPanel 文件管理器来编辑 robots 文件。然而，这很费时间，而且有点困难。

# WordPress 机器人插件

编辑 Robots 文件的最好方法是使用插件。有几个 WordPress。txt 插件在那里。我更喜欢 Yoast SEO。这是 WordPress 最好的 SEO 插件。我已经分享了如何设置 Yoast SEO。因此，这个插件允许你从你的 WordPress 管理区修改 robots 文件。不过，如果不想用 Yoast 插件，可以用 WP Robots Txt 之类的其他插件。一旦你安装并激活了 Yoast SEO 插件，进入 WordPress 管理面板> SEO >工具。

然后点击“文件编辑器”。之后，你需要点击“创建 robots.txt 文件”。然后你会得到 Robots.txt 文件编辑器。您可以从这里配置您的 robots 文件。在编辑文件之前，您需要理解文件的命令。主要有三个命令。

用户代理—定义搜索引擎机器人的名称，如 Googlebot 或 Bingbot。您可以使用星号(*)来指代所有搜索引擎机器人。不允许—指示搜索引擎不要对您站点的某些部分进行爬网和索引。允许—指示搜索引擎对您要索引的部分进行爬网和索引。

以下是 Robots.txt 文件的示例。

> 用户代理:*
> Disallow:/WP-admin/
> Alow:/

这个机器人文件指示所有搜索引擎机器人抓取网站。在第二行，它告诉搜索引擎机器人不要抓取/wp-admin/部分。在第三行，它指示搜索引擎机器人抓取并索引整个网站。

# 更好的搜索引擎优化设置

Robots 文件中的一个简单的错误配置可以完全从搜索引擎中删除你的站点。例如，如果您在 Robots 文件中使用命令“Disallow: /”,您的网站将被搜索引擎取消索引。所以在配置时你需要小心。

另一个重要的是 Robots.txt 文件对 SEO 的优化。在讨论机器人 SEO 的最佳实践之前，我想提醒你一些不好的做法。

*   WordPress Robots 文件隐藏低质量的内容。最佳实践是使用 noindex 和 nofollow meta 标记。你可以通过使用 Yoast SEO 插件来做到这一点。
*   Robots.txt 文件来停止搜索引擎索引你的类别、标签、档案、作者页面等。您可以使用 Yoast SEO 插件为这些页面添加 nofollow 和 noindex meta 标签。
*   使用 Robots.txt 文件处理重复内容。还有其他方法。

# 让机器人文件搜索引擎友好。

首先，你需要确定你的网站的哪些部分你不希望搜索引擎机器人抓取。我更喜欢禁用/wp-admin/、/wp-content/plugins/、/readme.html、/trackback/。其次，Robots 文件上的“Allow: /”衍生品并不重要，因为无论如何，机器人都会爬上你的网站。但是您可以将它用于特定的机器人。将站点地图添加到 Robots 文件中也是一个很好的做法。另外，阅读这篇关于 WordPress 网站地图的文章。

这是一个理想的例子。WordPress 的 txt 文件。

> 用户代理:*
> 不允许:/wp-admin/
> 不允许:/readme.html
> 允许:/wp-admin/admin-ajax.php
> 
> 禁止:/wp-content/plugins/
> 允许:/wp-content/uploads/
> 
> 不允许:/trackback/
> 
> 网站地图:https://visualmodo.com/post-sitemap.xml
> 
> 不允许:/go/
> 网站地图:https://visualmodo.com/page-sitemap.xml

# 谷歌网站管理员工具 WordPress 机器人测试

更新 Robots.txt 文件后，您必须测试 Robots.txt 文件，以检查是否有任何内容受到更新的影响。

您可以使用 Google 搜索控制台来检查您的 Robots 文件是否有任何“错误”或“警告”。只需登录谷歌搜索控制台并选择网站。然后进入 Crawl > robots test er，点击“提交”按钮。会弹出一个盒子。只需点击“提交”按钮。

最后，重新加载页面并检查文件是否更新。更新 Robots 文件可能需要一些时间。如果它还没有更新，你可以在框中输入你的机器人文件代码，检查是否有任何错误或警告。它将在那里显示错误和警告。救援

如果您注意到文件中有任何错误或警告，您必须通过编辑 robots 文件来修复它。