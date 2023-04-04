# WordPress 重定向创建指南

> 原文：<https://medium.com/visualmodo/wordpress-redirects-creation-guide-c3931df9eb2a?source=collection_archive---------0----------------------->

你想在 WordPress 中创建一个重定向吗？不确定什么是重定向，为什么它很重要？不要担心，我们已经在这本 WordPress 重定向初学者指南中介绍了你，我们将介绍什么是重定向，如何在 WordPress 中创建重定向，为什么你需要，以及什么时候你应该使用重定向。

从技术上讲，这不仅仅是一个 WordPress 重定向，而是一个 web 重定向，告诉浏览器 X URL 不再可用，应该转到 Y URL。无论您的站点是在 Wix、Drupal 上，还是只是一个普通的 HTML 站点，URL 重定向都可以用几乎相同的方式完成。不管你用什么[平台](https://awards.visualmodo.com/)。

# WordPress 重定向教程

![](img/0ad06a2c599dfbb64ae1964d39860133.png)

有许多不同种类的重定向，每一种都有不同的数字代码，所以让我们先来分解一下。最常见的两种是 301 和 302，这也是我们今天要重点介绍的。

301 —永久重定向。当你永久改变 URL 或站点结构时，你可以使用这些。所有旧链接的搜索引擎优化能力和排名都转移到新的。对于所有的意图和目的，旧的网址只是变成了新的。

302 —临时重定向。当你需要短期改变时，你可以使用这些。也许是网站重新设计或快速修复一个错误或故障。没有链接-果汁或排名被转移。

还有 300、303、304、307 和 308 重定向。但是这些都是为非常特殊的情况保留的，包括 POST 和 GET 的特殊用法，我们 95%的人都不需要。如果你对这个话题感兴趣，[Mozilla 开发者网络有一些关于不同种类重定向的精彩文档](https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections)。但是就你的 WordPress 重定向而言，你会经常使用 301，偶尔会使用 302。

# 。htaccess

网站最重要的文件之一是*。* [*htaccess*](https://visualmodo.com/fix-wordpress-internal-server-error/) 文件。代表*超文本访问*，显而易见，你可以通过它批准、拒绝或重定向对你网站的访问。虽然这看起来有点吓人，因为不做任何错事是非常重要的，但是对重定向文件的实际编辑是非常简单的。

使用你最喜欢的 FTP 程序(可能是 [FileZilla](https://visualmodo.com/best-ftp-client-wordpress/) )进入 WordPress 安装的根目录。就在核心文件夹下，您应该会看到 *.htaccess.*

对于 WordPress 重定向，你所要做的就是在上面写着 *# BEGIN WordPress* 的那一行上面添加一行简单的代码。

`Redirect 301 / http://visualmodo.com/`

或者

`Redirect 302 / http://visualmodo.com/`

请注意，这两行代码都会将您的整个站点重定向到指定的 URL。如果你想在你的站点中重定向一个特定的页面、文章或 URL，你需要提供它和目标 URL。两者都可以是相对路径(如果您在同一个域中),并用一个空格隔开。

`Redirect 301 /blog_post https://www.visualmodo.com/category/blog_post`

或者

`Redirect 302 /blog_post2.html /category/blog_post2.html`

此外，如果需要更复杂的东西，也可以将条件逻辑与正则表达式结合使用。这里有一个真正的[可怕的特殊重定向列表](https://gist.github.com/ScottPhillips/1721489)你可以这样使用。

无论您选择哪条路线进入重定向，您都需要保存您的*。htaccess* 文件作为明文，然后再将其重新上传到服务器。

# 插件使用

如果你不喜欢编辑*。htaccess* 文件进行 WordPress 重定向，不用担心。你不需要。因为你用的是 WordPress，所以有一个插件。因为 WordPress。其中一个叫做[快速页面/帖子重定向](https://wordpress.org/plugins/quick-pagepost-redirect-plugin/)，它开箱即用，非常好用。

设置重定向非常简单。激活后，快速重定向会向您的管理仪表板添加一个名为快速重定向的新项目。WordPress 重定向的默认类型是 301(毕竟这是最常见的)，你只需在几个字段中输入源 URL 和目的 URL 就可以设置它们。点击保存按钮，你就成功了。

此外，您将看到一个现有重定向的列表(注意上图中我使用的都是相对路径，而不是新的域，但这也是可能的)。如果你不再需要重定向，你可以点击它，或者你可以出于任何原因编辑重定向。对我来说，这是当我香肠手指一个难以辨认的错别字。

最后，如果你研究一下重定向选项，你会发现你可以做的选择非常多，要么创建适用于所有重定向的规则，要么启用适用于自定义帖子类型和元框等的设置。这是一个很大的改动

在切换到*快速重定向*之前，我过去也使用过[重定向](https://wordpress.org/plugins/redirection/)插件，因为重定向也允许 404 页面监控。你可以看到哪些页面丢失了，并设置一个 WordPress 重定向规则，这样任何访问该页面的人都会被发送到一个真正有用的页面。

# 最后的话

无论你的网站已经搬到一个新的位置，你正在改变你的永久链接结构，或者不知何故一个 WP 更新打破了你的安装的一切，你正在重新开始…有一个如何设置 WordPress 重定向的工作知识是非常方便的。

如果你喜欢挖掘核心文件或者更喜欢使用插件，这都没关系。两者都是有效的，最后达到的效果是一样的。所以不要害怕。开始尝试，看看什么最适合你。你甚至可以找到一种方法，只需点击几下鼠标就能提高排名和搜索引擎优化。