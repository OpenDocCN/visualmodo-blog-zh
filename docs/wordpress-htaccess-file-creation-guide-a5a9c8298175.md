# WordPress Htaccess 文件创建指南

> 原文：<https://medium.com/visualmodo/wordpress-htaccess-file-creation-guide-a5a9c8298175?source=collection_archive---------1----------------------->

在本指南中，我们将向你介绍 WordPress。htaccess 文件，解释它如何工作，它的目的，并讨论如何创建和编辑它。htaccess(超文本访问)文件是运行 Apache 软件的 web 服务器的配置文件。该文件通常控制它所在的目录以及父目录中的其他目录。使用可以添加或控制许多功能。htaccess 文件。一些基本特征是:

> 设置 301 重定向
> 
> 密码保护目录
> 
> 重写 URL
> 
> 缓存控制

![](img/f7a1efb182abc3c12acd8a51d02b12e6.png)

# 用途和目的

该文件的目的是重新配置 Apache Web 服务器的特定设置。因此，当打开或关闭服务器的某些功能时，它可以被证明是有用的。例如，该文件的一个典型用例是创建从非 www 到 www URLs 的重定向，反之亦然。

其他用途包括为某些文件设置权限，阻止机器人或添加 MIME 类型。这对于维护你的 WordPress 的安全设置特别有益。这些特性在 WordPress 开发过程中会派上用场，因为你必须配置一些最适合你需求的设置。

在大多数情况下。默认情况下，每个 WordPress 安装都有 htaccess 文件。但有时它会隐藏在安装根文件夹中。以下是 [WordPress](https://developer.wordpress.org/) htaccess 文件的默认代码:

> 重写者^index\.php$ — [L]
> 第二次重写% {请求文件名}！-f
> 第二次重写% {请求文件名}！-d
> 重写器。/index.php [L]
> # END WordPress

现在如果你想在你的 WordPress 中添加一些代码。htaccess 文件，或者您想创建一个新的文件，但您不知道如何做到这一点，那么你就在正确的地方。首先我会告诉你如何找到 WordPress。cPanel 中的 htaccess 文件。

# cPanel 中的 WordPress htaccess 文件在哪里？

一般来说，当你在网络主机上安装 WordPress 的时候，这个文件就已经创建好了。但是以句点开始的文件名将使文件隐藏在文件夹中。

登录到您的 cPanel，点击文件管理部分下的文件管理器。当你点击文件管理器时，会弹出一个小窗口，你可以在打开文件管理器时找到几个选项。WordPress 安装根目录是默认的。htaccess 文件位置。确保选中“显示隐藏文件(点文件)”复选框。然后点击 Go。

现在你可以看到了。文件列表中的 htaccess 文件。右键单击该文件，然后单击编辑。一个带有文本编辑器的新窗口将会打开。您可以编辑您的。htacces 文件并保存编辑器中的更改。使用 FTP 服务器访问文件管理器。您可以使用 FTP 客户端(FileZilla)访问文件。

# 在 cPanel 中创建 WordPress htaccess 文件

如果没有。htaccess 文件，你可以很容易地从你的 cPanel 创建一个。下面是创建该文件的方法。按照上述步骤访问您的文件管理器。现在在你屏幕的左上方，你会看到一个选项——“新建文件”。当你点击“新建文件”时，会弹出一个小窗口。您可以在这里设置文件名和目录。按照下面的图像。

现在放。新文件名字段的 htaccess。记住。htaccess 不是扩展。这是文件名。在经期之前什么都没有。不应该是 text.htaccess 之类的，只是. htaccess，现在点击“新建文件”。重新加载您的文件管理器。你会发现新创建的。列表上的 htaccess 文件。

# 编辑 htaccess 文件的插件

如果您不想访问您的文件管理器或 FTP 来编辑您的。htaccess 文件，你可以使用插件来编辑它。比如 Yoast 的 WordPress SEO 就有编辑你的 Robots.txt 和。htacces 文件从您的仪表板。

# 结论

[。htaccess 文件](https://visualmodo.com/increase-wordpress-maximum-file-size-upload/)是 WordPress 正常工作所必需的。它可以提供 web 服务器附加功能的句柄，特别是当它们与安全设置相关时，如防止垃圾邮件、阻止不良机器人等。现在你已经对 WordPress 有点熟悉了。htaccess 文件，你可以继续进一步探索它的可能性，以改进你的 WordPress 项目。