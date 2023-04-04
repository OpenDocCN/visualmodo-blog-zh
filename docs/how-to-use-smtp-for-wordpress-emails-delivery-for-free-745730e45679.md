# 如何使用 SMTP 免费发送 WordPress 邮件？

> 原文：<https://medium.com/visualmodo/how-to-use-smtp-for-wordpress-emails-delivery-for-free-745730e45679?source=collection_archive---------0----------------------->

你愿意使用免费的 SMTP 服务器来发送你的 WP 网站邮件吗？通常情况下，WordPress 使用 PHP 电子邮件功能，这是不可靠的，经常会将您的电子邮件标记为垃圾邮件。因此，SMTP 服务器是确保从 WordPress 网站发送电子邮件的最佳方式。

# 免费发送 WordPress 邮件的 SMTP 服务器

![](img/d582abd58de64fe09b18ef013d034f6e.png)

首先，按照我们教程中关于如何安装 WordPress 插件的说明，安装一个名为 WP Mail SMTP 的插件。一旦插件被读取并激活，一个新的项目将出现在设置部分“电子邮件”下。你需要导航到它来配置 WordPress 来使用 SMTP。

# 免费插件设置

在此页面上，您将看到几个可用的配置选项。这里列出了所有这些设备，以及它们的配置:

发件人电子邮件:您要发送电子邮件的电子邮件地址。举个例子，email@yoursite.net。

发件人姓名:您的电子邮件将显示的姓名。

mailer——选择是否要使用*默认* PHP mail()函数*、Gmail/G 套件账户、Mailgun、SendGrid* 或*其他 SMTP WordPress 服务器*。选择*默认*模式将使用 PHP mail()函数发送消息，无需 [SMTP 认证](https://visualmodo.com/setup-smtp-wordpress-email-delivery/)。 *Gmail/G 套件、Mailgun* 和 *SendGrid* 选项需要额外的信息，如客户端 id 和客户端密码或 API 密钥，这些信息应在相应的提供商处获得。*其他 SMTP 服务器*选项将提示您输入其他配置细节，我们将在下面进行描述。

# 额外的 SMTP WordPress 选项

返回路径:检查您是否希望您的电子邮件的返回路径与发送电子邮件的路径相匹配。此外，如果您选择*其他 SMTP 服务器*作为邮件程序，系统会提示您添加 SMTP WordPress 服务器的配置设置。

SMTP 主机:您的 SMTP 服务器的主机名。

SMTP WordPress 端口:服务器工作的端口。

加密:如果该主机名有可用的 SSL/TLS 加密，请在此选择它。

自动 TLS:如果您的服务器支持 TLS 加密。所以，启用这个选项。

验证:检查您的 SMTP 服务器是否需要验证。

用户名:您的 SMTP 服务器的用户名。

密码:最后，您的 SMTP 服务器的密码。

配置完这些参数后，单击页面底部的保存设置。