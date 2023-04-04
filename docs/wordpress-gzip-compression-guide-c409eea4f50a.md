# GZIP 压缩指南

> 原文：<https://medium.com/visualmodo/wordpress-gzip-compression-guide-c409eea4f50a?source=collection_archive---------1----------------------->

为 WordPress 启用 GZIP 压缩，以一种简单的方法使你的页面加载更快，并保持你的网站以最高速度运行

如果你已经用计算机工作了一段时间，你可能已经熟悉了压缩。对于那些不喜欢压缩的人来说:压缩是一个非常有用的工具，可以将一堆文件组合成一个更小(更容易传输)的文件，对于网站来说，这可以显著加快页面加载速度。在这篇文章中，我将看看 gzip 压缩是如何工作的，以及如何在你自己的 WordPress 支持的网站上启用它。

# 这是什么？

![](img/d3ab73a51724b3c8b9fae8c1a4d86096.png)

在继续讨论如何实现它之前，让我们先来看看压缩意味着什么以及它如何提供帮助。

如今，几乎所有的现代网站都混合使用了 T2、HTML、CSS 和 JavaScript，由程序员以一种合乎逻辑的、全球通用的方式编写。这样做的结果几乎总是会产生相当大的开销，除了可读性之外没有任何用处。此外，大多数程序员还会使用各种设计模式和公共元素，从而导致大量的重复。

gzip 等压缩算法使用文本中的模式和重复来创建更有效的数据存储方式。让我们看一个例子。

下面是一些使文本以粗体显示的 HTML 代码:

```
<strong>this is bold</strong>
```

这个的压缩版其实挺长的:`eNqzKS4pys9LtyvJyCxWAKKk/JwUG32oIC8XALn8Cuo=`。但是，看看当我们压缩以下内容时会发生什么:

```
<strong>this is bold</strong>
<strong>this is bold too</strong>
```

压缩版是`eNqzKS4pys9LtyvJyCxWAKKk/JwUG32oIC+XDRZphZL8fCQlACNDF0U=`。尽管原始文本的大小增加了一倍多，但压缩版本实际上只增加了 16 个字符——大小减少了 32%，这意味着加载量更少，网站速度更快。

# WordPress 的 GZIP 压缩

![](img/8157937f753d69a3aa9ef1ddcbb43822.png)

理解 gzip 压缩不是 WordPress 负责的事情是很重要的。它实际上是由服务器自己处理的(而不是在 [WordPress](https://visualmodo.com/blog/) 中)，这意味着要启用它，你必须在 WordPress 之外进行设置。

# 主办公司

首先:由于启用压缩需要您编辑(甚至创建)一个不容易处理的敏感文件(称为' [htaccess 文件【T7])，如果您对该做什么有任何疑问，最好让您的主机为您做这件事。如果你和一个有顶级支持的顶级主机在一起，他们应该能在几分钟内为你设置好(如果他们还没有的话)。](https://en.wikipedia.org/wiki/.htaccess)

# 设置

htaccess 文件用于向服务器发出特殊的指令，比如重定向、自动为某些请求预先准备或附加文件，以及其他各种各样的功能——比如启用 gzip 压缩！自己设置的棘手之处在于定位——然后编辑——这个麻烦的文件。

首先，您需要一种方法来访问服务器上的文件。大多数人的首选方法几乎肯定是通过 FTP。然而，因为一个网站的被压缩文件是一个“[点文件](https://en.wikipedia.org/wiki/Dot-file)”(意味着它通常是隐藏的)，所以比大多数网站更难找到。更糟糕的是，因为它是一个隐藏的文件，如果你像下载普通文件一样把它下载到你的电脑上，它将保持隐藏状态，编辑起来非常麻烦。

**重要提示:**如果这一切听起来有点可怕，那么在你有了更多的经验之前，你最好离开它，因为这不是一个真正深入必要基础知识的地方，比如如何使用 FTP 客户端，如何在服务器上或服务器外编辑文件，或者如何处理点文件。

另一方面，**如果你已经熟悉了这些东西**，那么你需要做的就是将下面的内容复制并粘贴到你站点的 htaccess 文件中:

```
<ifModule mod_gzip.c>
mod_gzip_on Yes
mod_gzip_dechunk Yes
mod_gzip_item_include file .(html?|txt|css|js|php|pl)$
mod_gzip_item_include handler ^cgi-script$
mod_gzip_item_include mime ^text/.*
mod_gzip_item_include mime ^application/x-javascript.*
mod_gzip_item_exclude mime ^image/.*
mod_gzip_item_exclude rspheader ^Content-Encoding:.*gzip.*
</ifModule>
```

就这样——全部完成！基于文本的内容，比如 HTML、CSS 和 JavaScript，现在应该以 gzip 压缩格式传输。

# 检查你的工作

有许多方法可以检查一个站点的文件是否被 gzip 压缩，其中最简单(也是最有趣)的方法是使用奇妙的 [GTMetrix](https://gtmetrix.com/) 站点测试工具——我们在以前的文章中已经介绍过:如何有效地使用 GTMetrix 测试一个网站的速度！

如果一切正常(而且，您可能需要像往常一样清空您站点的缓存和/或等待几分钟才能生效)，您应该能够在您站点的 GTMetrix 结果的“瀑布”部分看到以下内容:简单！

# 结论

Gzip 压缩是添加到(或已经添加到)你的网站的简单速度修正之一——不管它是由 WordPress 还是其他方式驱动的。如果你不启用它，你可能会错过一个重大的速度提升。

最后一点:如果你有兴趣了解一个网站的 htaccess 文件，我推荐你看一下 Tuts+的优秀 htaccess 指南，它包含了更多的信息和一些很棒的小知识，你可以用它来为你的网站服务。