# WordPress 数据库文件替换

> 原文：<https://medium.com/visualmodo/wordpress-database-files-replacement-9177e3ddc10d?source=collection_archive---------0----------------------->

你想在 WordPress 数据库中进行大规模搜索和替换吗？无论你想查找和替换一个特定的文本、URL 或者图片，你都可以通过使用一个查找和替换 WordPress 插件或者一个简单的 SQL 查询很容易地做到。在这篇文章中，我们将向你展示如何在你的 WordPress 数据库中查找和替换文本。

# 搜索 WordPress 数据库

通常，没有办法从你的仪表板中搜索和修改你的数据库。这是故意的，因为数据库是你网站的神经中枢。从用户名、电子邮件到网址和 WooCommerce API 密钥和令牌，所有东西都存储在那里。DB 很重要。并且能够随意编辑它是危险的。

![](img/124c264f04dadeef0ff1b121cd0c904d.png)

通常，您需要通过 phpMyAdmin 这样的工具来编辑数据库表。一般来说，你可以在你的主机的 cPanel 中找到这个，你猜对了，在**数据库**下。一旦进入，你就有了选项、表格、数字和标签……嗯，你可以自己看。

左边所有的都是你的主机的数据库，通常代表一个 WP [安装](https://visualmodo.com/wordpress-themes/)。然后，当您单击其中一个时，您会看到针对存储的所有不同类型的数据的所有选项。现在，您点击**搜索**，您将看到该表中的数据。*现在*你可以开始寻找和替换。

那太多了。这真的很容易让人感到困惑和困惑，并像这样完全转向。因此，如果您需要编辑、更改或迁移数据库中的任何类型的数据，那么 *Better Search and Replace* 插件可能是一个不错的选择。这就是我们免费且简单的插件解决方案的用武之地！

# WordPress 插件

当你从 [WordPress 插件库](https://wordpress.org/plugins/better-search-replace/)安装插件时，你会得到一个新的设置菜单，出现在**工具**下，名为**更好的搜索替换**。

在这个新的插件中，你会得到一个比 phpMyAdmin 更友好的用户界面。最好的部分是这个插件**将数据库限制在这个 WordPress 安装**上。所以不用担心会影响其他网站。这里主要有三点需要注意。

# 取代

很直接，真的。无论您在寻找什么值，无论是哪个表(或多少个表)，都将被输入到这里。例如，如果您要编辑包含您不想提及的特定网站名称的所有评论，您可以在第一个字段中输入网站名称，然后在第二个字段中输入密文。

# 选择表格

根据搜索的深度和广度，您可以选择要更改的表。例如，如果你只是想改变评论区，你可以通过 CTRL/CMD 点击来选择标有 comments 和*comments meet*的评论区。

# 运转

我认为这是他们给你的最重要的选择。由于数据库非常敏感，所以执行模拟运行会给你一个模拟或者会发生什么。只需输入您的信息，并保持检查，以获得关于哪些表和哪些字段将被更改的报告。如果你问我的话，在你对你的网站做任何永久性的改变之前，首先必须这样做。

# 使用插件

使用[插件](https://visualmodo.com/wordpress-membership/)本身真的很简单。举个例子，我将带你去改变 WordPress 管理员的用户名。是的，同样的用户名默认为*管理员*，或者在个人资料旁边有一个警告，说不能更改。这是数据库操作的一种用例，它使*更好地搜索，并取代了*的优势。

首先，您可以看到 WP 网站的用户列表。

我的目标是把诺兰·索兰托的用户名从*顶级狗*改成 *IOI-655321。*通过这样做，他将使用替换的用户名登录，并且该用户名在站点中使用的任何地方也将被替换。

我正在用 CTRL/CMD-click 突出显示所有的表，在字段中输入我的搜索和替换术语，并确保我先做了一次预演。

如您所见，原始用户名的唯一实例在 *users* 和 *usermeta* 表中。完美。现在，取消预演，执行真正的搜索和替换。之后，您将在横幅中看到单元格实际上被更新了，这也在模态中得到验证。此外，您可以看到操作工具不是 0.001 秒，而是 0.004 秒和 0.003 秒，因此您可以看出在幕后发生了实际的计算。

当我们返回到**用户**页面时，您可以看到更改已经生效，用户名是全新的。

你甚至可以进入用户本身，看到灰色的外场已经改变。*用户名不能改*，嗯？我给你看，WordPress 文档！

# 最后的话

我认为这是一种更好、更优雅的处理 WordPress 数据库的方式。您可以使用它进行任何数量的更改，包括 web 地址(例如，将所有文件位置从 *localhost.dev* 更改为【elegantthemes.com】T2)。能够理解和使用 WordPress 数据库对于你作为一个开发者(我想说，也是一个用户)的成长是至关重要的。但是有些工具非常吓人。希望*更好的搜索和替换*已经告诉你没有任何理由被吓倒。