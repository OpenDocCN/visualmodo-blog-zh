# Dropbox WordPress 备份指南

> 原文：<https://medium.com/visualmodo/dropbox-wordpress-backup-guide-f59494349ef4?source=collection_archive---------0----------------------->

Dropbox 成立于 10 多年前的 2007 年，但它已经在各种不同的个人中流行起来，无论是需要一个安全存储个人文件的地方的普通人，还是需要一个中心位置来安全存储企业宝贵数据的商务人士。你可以通过这项服务做很多事情，但我们将专注于一个特定的任务——Dropbox WordPress 云备份，这意味着你不必依赖你的托管公司为你做这件事。

我们将推出几个不同的插件，允许你备份你的 WordPress 站点，并将其存储在云中，特别是在 Dropbox 帐户中。我们将首先回顾一下为什么要以这种方式存储备份，然后再深入探讨几个以不同方式处理备份的免费和高级插件。

# Dropbox WordPress 备份

![](img/ad1705c1804ee8f3e95953942dbac450.png)

幸运的是，有很多 WordPress 插件可以让你自动将网站备份到 Dropbox。 [WordPress 备份到 Dropbox](https://wordpress.org/plugins/wordpress-backup-to-dropbox/) 是最好的插件。它可以自动备份 WordPress 数据库(文章、评论等)和 WP 内容文件夹(主题、插件、图片等)。

下面是如何设置这个插件。如果你没有 Dropbox [账户](https://awards.visualmodo.com/)，去 Dropbox.com 注册吧。现在登录你的 WordPress 仪表盘。进入插件>添加新插件，搜索“WordPress 备份到 Dropbox”。点击“立即安装”按钮并激活插件。

一旦你激活了插件，你会注意到在你的 WordPress 仪表盘下面有一个名为“WPB2D”的新菜单项。将光标悬停在 WPB2D 菜单上，然后单击“备份设置”。现在它会要求你用你的 Dropbox 账户授权这个插件。只需点击“授权”按钮。然后一个新的窗口将会打开，Dropbox 将会要求你验证并授予插件访问权限。点击“允许”按钮。

一旦 WordPress 备份到 Dropbox 插件连接到你的 Dropbox，它会自动创建一个名为“wpb2d”的备份文件夹来存储所有的备份文件。

# 您的需求

将备份存储在 wpb2d 应用程序文件夹的子文件夹中:如果您计划在同一个 Dropbox 帐户中备份多个站点，请选中此框并给子文件夹命名。日期和时间:设置备份到 Dropbox 的日期和时间。如果你正在运行一个大型的 WordPress 博客，选择一个流量较少的日子，比如周末。

频率:设置备份到 Dropbox 的频率。我个人更喜欢每周备份。您可以选择每日备份，因为它只备份增量。排除的文件和目录:选择要从备份中排除的文件和目录。通常你可以排除 wp-admin，因为你可以从 WordPress 安装中获得它。您也可以排除缓存文件夹。大多数时候，它们被命名为 wp-content/cache/、wp-content/tmp/、wp-content/w3tc/等等。

最重要的文件夹是“wp-content ”,因为它包含了你所有的上传，主题，插件等等。你不应该排除它。单击“保存更改”,它将显示下次备份计划时间。现在是时候进行第一次备份了。只需点击“WPB2D”菜单下的“备份监视器”。然后点击“开始备份”。这可能需要时间(可能几个小时),取决于您站点的大小。备份完成后，登录您的 Dropbox 帐户并检查备份。

# 更多选项

# 克隆主人

WordPress Backup &[Clone](http://codecanyon.net/item/wordpress-backup-clone-master/5901461)Master 是一个用于备份、恢复、克隆和迁移的高级插件。它创建完整的 WordPress 备份，包括数据库、设置、主题、插件和图像。它会自动将备份上传到你的 Dropbox 账户。这个插件将花费你 37 美元。价格是完美的，因为它有这么多的功能。

# 后退

BackWPup 是免费的 WordPress [插件](https://wordpress.org/plugins/backwpup/)，它可以安排将你的 WordPress 站点自动备份到 Dropbox 和其他云存储服务，如亚马逊 S3、微软 Azure 等。它会在中创建一个备份。这样你就可以很容易地恢复你的 WordPress 站点。它有免费版和高级版。免费版本包括数据库备份，WordPress XML 导出，文件备份，优化和修复数据库等。

# 管理工作

ManageWP 是一个管理和备份你的 WordPress 站点的网站和插件。它允许你从一个仪表板管理多个 WordPress 站点。它还允许您计划备份到云存储服务，如 Dropbox、亚马逊 S3、Google Drive 和 FTP / SFTP。

它有免费和收费服务。对于 Dropbox 备份，您必须购买每月 2.40 美元的高级计划。

# UpdraftPlus

UpdraftPlus 是另一个流行的 WordPress [插件](https://wordpress.org/plugins/updraftplus/)，用于备份和恢复。它提供完整的备份到 S3，Dropbox，谷歌驱动器，Rackspace，FTP，SFTP，电子邮件+其他。这个插件最好的一点是快速恢复。只需单击一下，您就可以恢复备份。

它有免费版和高级版。对于高级版本，两个网站的价格为 70 美元，10 个网站为 95 美元，无限网站为 145 美元。

# 最后的话

类似于投资:你不会把所有的积蓄都投入到一个共同基金中。因为如果失败了，你就有大麻烦了。同样的道理也适用于备份你的[网站](https://shots.visualmodo.com/)文件和数据库。

不要只在服务器级别进行备份。事实上，WordPress 建议保留三个不同的备份副本——都在不同的媒介中(比如 CD、硬盘、桌面、云等等)。对于我最重要的网站，我在本地维护一个最新的数据库版本(在我的 MAMP 上)。