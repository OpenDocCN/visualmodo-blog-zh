# WordPress MailChimp 订阅者弹出窗口

> 原文：<https://medium.com/visualmodo/wordpress-mailchimp-subscriber-popup-883c1c5713da?source=collection_archive---------1----------------------->

在你的 WordPress 站点上显示一些优势或推广的订阅者弹出添加，这是一个获得你的电子邮件列表订阅者的极好方法，参见这篇文章中如何在你的 WordPress 上使用 MailChimp 表单。

# 介绍 MailChimp 订户弹出窗口

向 WordPress 添加 MailChimp 订阅表单有很多方法。我倾向于使用 MailChimp 提供的嵌入式表单、Gravity Forms MailChimp 插件或者优秀的用于 WordPress 插件的 MailChimp。随着弹出式表单在网站上越来越受欢迎，MailChimp 为所有 MailChimp 计划发布了一个出色且非常灵活的弹出式订阅表单。最棒的是 MailChimp 弹出窗口看起来很漂亮，完全免费，而且非常容易安装在网站上。唯一的问题是这种形式在 WordPress 网站上不起作用。

![](img/b11058ab6236f13cc9b79f4338e13f94.png)

那么，为什么 MailChimp 订阅者弹出窗口在 WordPress 中不起作用呢？

根据你的 WordPress 版本和主题，在所有的 [Visualmodo WordPress 主题中](https://visualmodo.com/wordpress-membership/)你可以很容易地在主题选项面板的“自定义代码”字段中输入 mailchimp 订阅者弹出代码，但是有些主题没有这个选项，所以看下面该怎么做:

当我第一次用 MailChimp 添加弹出代码时，我注意到当我加载任何本应出现弹出窗口的 WordPress 网站页面时，没有任何反应。我搜索了谷歌，注意到许多其他人也有同样的问题，但找不到任何人实际上在 WordPress 中有弹出窗口。我将 MailChimp 提供的代码放在页眉和页脚中进行了测试，但都不起作用。我的代码看起来类似于:

`<script``type="text/javascript"``src="//s3.amazonaws.com/downloads.mailchimp.com/js/signup-forms/popup/embed.js"`

`</script>`

`<script` `type="text/javascript">`

`require(["mojo/signup-forms/Loader"], function(L)`

`{ L.start({"baseUrl":"mc.us2.list-manage.com","uuid":"7407194612ca922bbc80e591z1","lid":"es713853t99"})`

`})</script>`

因为 MailChimp 提供的弹出窗口比第三方解决方案和大多数其他支持弹出窗口的 WordPress 插件优雅得多，所以我决定做一些故障排除。没多久就发现`//s3.amazonaws.com/downloads.mailchimp.com/js/signup-forms/popup/embed.js`处的 MailChimp 文件试图从域的根目录加载 jquery.js 文件。

在 WordPress 中，jquery.js 是一个核心脚本，由 WordPress 在位置`/wp-includes/js/jquery/jquery.js`提供。WordPress 支持的网站的根目录中没有 jquery.js 文件，因此弹出窗口无法加载。

# 让 MailChimp 订阅者弹出窗口在 WordPress 中工作的说明

首先，需要一份免责声明；接下来的解决方案是一个黑客，违背了 WordPress 的最佳实践。我相信有一个更好的解决方案，如果有人知道，请告诉我。
下面是指令(我们下面要做的是创建 MailChimp 代码想要加载的 *jquery.js* 文件，但是在我们创建的文件中，我们实际上加载的是 WordPress 提供的版本 *jquery.js* ):

1.  设计你的 MailChimp 弹出窗口并复制代码。
2.  在 WordPress 中安装并激活[页眉和页脚插件](https://wordpress.org/plugins/header-footer/)。
3.  在 WordPress 中，进入*设置- >页眉和页脚*。在*页眉和页脚*选项卡中，将 MailChimp 弹出代码粘贴并保存到*代码中，该代码将被添加到页面*文本区的末尾之前。
4.  打开文本编辑器，将以下内容粘贴到新文件中

`jQuery.getScript("/wp-includes/js/jquery/jquery.js")`

`.done(function() {`

`})`

1.  使用 FTP 或 cPanel 文件管理器将新创建的 *jquery.js* 复制到您的域的根目录(这通常是 cPanel 中的 *www* 目录或 *httpdocs* 目录，如果您使用 Parallels Plesk Panel)。

当你在你的网站上加载任何页面时，你的订阅者弹出窗口现在应该可以工作了。请记住，MailChimp 弹出窗口是经过编码的，因此如果访问者订阅或单击弹出窗口关闭按钮，表单将不会再次显示给他们(也就是说，不要误以为弹出窗口实际上不起作用)。该表单记得不要通过使用 cookie 再次显示弹出窗口，因此从浏览器中清除 cookie 将强制弹出窗口再次显示。