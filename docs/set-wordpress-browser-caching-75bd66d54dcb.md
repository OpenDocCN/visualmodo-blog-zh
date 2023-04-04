# 设置 WordPress 浏览器缓存

> 原文：<https://medium.com/visualmodo/set-wordpress-browser-caching-75bd66d54dcb?source=collection_archive---------0----------------------->

你正在寻找一个简单的解决方案来利用 WordPress 中的浏览器缓存吗？或者你可能需要手动使用浏览器缓存。我们将解释提高你的网站加载速度的方法。

缓存是最有效的方法之一，以确保您的网站加载速度更快，为您的访客。然而，为了获得最佳结果，你的站点应该告诉浏览器他们需要缓存什么内容。[缓存](https://visualmodo.com/best-wordpress-cache-plugins/)插件通常不会让你完全控制这些设置，所以要靠你手动配置。

幸运的是，WordPress 能让你相当简单地做到这一点。只需要对你的*做一些改变。htaccess* 文件。在本文中，我们将更多地讨论什么是浏览器缓存，如何检查您的网站是否正确利用它，以及如何配置它。我们开始工作吧！

# 浏览器缓存

![](img/cfcf9710197be5e7867ec3b013138712.png)

理想情况下，当有人访问你的网站时，他们的浏览器会在本地保存一些内容，这样就不必在以后的访问中重新加载。这种做法被称为“浏览器缓存”,这就是为什么在您的网站上实施是一个好主意:

**减少装载时间。用户需要加载的资源越少，你的站点应该呈现得越快。**

**潜在的较低跳出率。加载时间和跳出率之间有直接关系。前者越高，访问者放弃你的网站的机会就越大。**

**它减少了服务器的工作量。由于回头客不需要从你的服务器上下载内容，所以你也不必努力跟上流量。**

重要的是要明白，在大多数情况下，你不希望浏览器缓存你的整个网站。现在许多网站都包含了大量不断更新的互动内容。这意味着如果用户缓存整个页面，他们可能会错过对页面的更改。

考虑到这一点，您需要对告诉浏览器缓存的内容进行挑剔。例如，图像、徽标和级联样式表( [CSS](https://visualmodo.com/) )不会经常改变。这意味着您可以简单地告诉浏览器缓存它们并指定一段时间。理想情况下，网站的缓存配置应该区分定期更新(或不定期更新)的文件类型。这样，用户就不必手动清空缓存来查看你对站点所做的任何更改。

# 检查缓存

当我们谈到利用 WordPress 缓存时，我们指的是配置你的网站，让浏览器知道他们需要在本地存储什么内容，以及存储多长时间。查明一个网站是否正确利用浏览器缓存的最简单的方法是使用一种工具，如 [Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) ，它可以分析这一设置和其他设置。首先，输入您网站的网址，然后点击*分析*按钮:

PageSpeed Insights 将对您的网站在移动和桌面上的优化进行评分。对于你网站的每个“版本”,你会得到一个 0-100 分的个人分数，以及如何改进的建议。PageSpeed Insights 在计算分数时考虑的一个关键因素是您的网站是否利用了浏览器缓存:

如果你正确配置了你的 WordPress 网站，你不会看到上面的消息，你应该会得到一个不错的 PageSpeed Insights 分数。请记住，Divi 在几个方面进行了优化，为您提供现成的体面的 PageSpeed Insights 评分。然而，有很多方法可以提高你网站的性能，学习这些方法是投入你时间的一个很好的方式。

# 设置 WordPress 浏览器缓存

在过去，我们已经讨论过缓存插件和最常用的选项。如果你不想弄乱你的 WordPress 站点的配置，这些类型的工具是极好的。但是，如果您不介意在核心文件中添加几行代码，您可以更好地控制浏览器缓存配置。在您继续之前，您应该准备好您网站的最新备份，以防万一！

# 网站 FTP

在下一部分，你需要访问你的*。htaccess* 文件并编辑它。最好的方法是通过专用客户端使用文件传输协议(FTP)。我们偏爱 FileZilla ，因为它包含了许多功能，而且使用起来相当简单。

首先，安装并执行客户端。你会在屏幕顶部看到四个空白字段，分别是*主机*、*用户名*、*密码*和*端口*:

您需要一组特定的 FTP 凭据才能使用此协议登录您的网站。在大多数情况下，当你注册托管服务提供商时，你应该已经通过电子邮件收到了。然而，你也应该能够在你的主机仪表板上或者通过 cPanel 找到它们。

一旦您有了凭证，输入它们并点击*快速连接*按钮。FileZilla 将与您的网站建立连接，一个或几个文件夹应该会出现在屏幕的右下角。其中一个应该是你的 WordPress *root* 文件夹(也叫 *www* ， *public_html* ，或者以你的网站命名)，它所有的文件都驻留在那里:

打开目录后，进入第二步！

# 编辑。htaccess 文件

[*。htaccess*](https://visualmodo.com/fix-wordpress-internal-server-error/) 是一个 WordPress 核心文件，指导你的服务器应该如何提供文件和页面。例如，如果你使用漂亮的永久链接。htaccess 将包含如何处理它们的说明。您还可以配置文件来阻止特定 IP 对特定页面的访问，等等。

在这种情况下，我们将使用*。告诉你的服务器缓存哪些文件。为此，请寻找*。htaccess* 文件在你的*根*目录下。点击右键，选择*查看/编辑*选项。这将使用本地文本编辑器打开文件，使您能够对其进行更改:*

在你添加任何新代码到你的*之前。htaccess* 文件，向下滚动直到你找到那一行。在大多数情况下(包括这种情况)，您希望在该行之前向文件中添加新代码。下面是一个简单的浏览器缓存配置示例，您可以立即实施:

expire active On
expires bytype image/jpg " access 1 year "
expires bytype image/JPEG " access 1 year "
expires bytype image/gif " access 1 year "
expires bytype image/png " access 1 year "
</if module>

例如，如果你正在运行一个 WordPress 博客，你可能不会经常修改你的文章图片或者你的网站标志。在这种情况下，我们可以将这些文件存储在访问者的浏览器缓存中很长一段时间，比如说一年。在上面的代码中，我们一下子涵盖了所有最流行的图像类型。每行的前半部分表示我们正在处理的文件的类型，第二部分为它设置一个到期日期:

ExpiresByType image/jpg "访问 1 年"

当然，并不是所有的内容都应该缓存一年，所以我们可以随意使用这个值。在本例中，我们添加了缓存 HTML、CSS 和 JavaScript 文件的说明:

 <ifmodule mod_expires.c="">expire active On
expires bytype image/jpg " access 1 year "
expires bytype image/JPEG " access 1 year "
expires bytype image/gif " access 1 year "
expires bytype image/png " access 1 year "
expires bytype text/CSS " access 1 week "
expires bytype text/html " access 1 month "
expires bytype text/x-JavaScript " access 1 week "</ifmodule>

这里，我们将 HTML 内容设置为在访问者第一次访问一个月后更新，这是一个合理的时间范围。另一方面，当你使用复杂的主题，比如 Divi，或者几个插件时，CSS 和 JavaScript 文件往往会发生变化。考虑到这一点，我们将它们的缓存到期日期设置为访问后一周。

当你用你的*实现那些规则的时候。htaccess* 文件，您将拥有一个坚实的浏览器缓存基础。让我们通过添加其他文件类型的说明来介绍我们的基础:

 <ifmodule mod_expires.c="">expire active On
expires bytype image/jpg " access 1 year "
expires bytype image/JPEG " access 1 year "
expires bytype image/gif " access 1 year "
expires bytype image/png " access 1 year "
expires bytype text/CSS " access 1 week "
expires bytype text/html " access 1 month "
expires bytype text/x-jav</ifmodule>

以 *ExpiresDefault* 开头的行为所有文件设置一个月的默认缓存时间。但是，您可以通过为特定文件类型添加缓存指令来覆盖它。这里的要点是捕捉其他可能不保证单独规则的文件类型，以进一步提高网站的加载时间。

现在，记得保存对你的 WordPress *的修改。htaccess* 文件并关闭你的文本编辑器。FileZilla 将询问您是否要覆盖*。htaccess* 文件，你应该说:“是”。现在继续使用 PageSpeed Insights 再次测试您的网站——浏览器缓存优化建议应该消失了！

# 最后的话

为你的网站启用缓存插件很容易。然而，它通常不能让你完全控制它存储在用户电脑上的内容类型，或者存储多长时间。手动方法使您能够为网站内容定制缓存配置，并且实现起来并不困难。

手动配置浏览器缓存只需对您的*做一些更改。通过 FTP 访问*文件。如果你不怕一点点代码，你应该可以很快地设置它。然后，你可以使用[Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)测试你的网站，看看它是否正确利用了浏览器缓存。