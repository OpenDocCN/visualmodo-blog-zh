# 从网站 URL 中删除 WWW

> 原文：<https://medium.com/visualmodo/removing-www-from-site-url-bcf690b4a7ee?source=collection_archive---------0----------------------->

删除 www 教程。如何将 www 从你网站的 URL 中删除？还是补充一下。在这篇文章中，我将向你展示如何通过调整你的。htaccess 文件。

# 从网站 URL 中删除 www

# 使用这样或那样的方法会影响 SEO 吗？

你可能想知道使用其中一个是否会对你的搜索引擎优化产生影响。答案是:不。这真的只是一个偏好/美学的问题。只要确保你在谷歌搜索控制台中正确地添加了 www 和非 www 域，正如这里的[所描述的](https://support.google.com/webmasters/answer/44231?hl=en)，以确保谷歌能够正确地索引你的网站。

![](img/c8a95f1024d0db4ba84b6473884b7b1a.png)

# 从您的域名中删除 www

```
RewriteEngine On
RewriteCond %{HTTP_HOST} ^www.example.com$ [NC]
RewriteRule ^(.*)$ [http://example.com/$1](http://example.com/$1) [R=301,L]
```

如果你喜欢推销你的网站没有 www 前缀，你可以添加以下行到你的。htaccess 文件(仅限 Apache):

编辑:正如 Thomas 在评论中指出的，修改。htaccess 文件。

**注意，Apache 的 mod_rewrite 模块需要启用。否则上面的片段就不行了。**

现在，在 Nginx 中，这个代码片段有一点不同，但是当放在适当的配置文件中时(这取决于您的设置)，会产生完全相同的[结果](https://visualmodo.com/):

```
server {
 server_name [www.example.com;](http://www.example.com;)
 return 301 [http://example.com$request_uri;](http://example.com$request_uri;)
}
```

现在只需重启 Nginx，您就可以开始工作了！

# 添加 www 而不是删除它

若要执行与上一节相反的操作，请将以下代码添加到您的。htaccess 文件:

```
RewriteEngine On 
RewriteCond %{HTTP_HOST} ^example.com$ 
RewriteRule (.*) [http://www.example.com$1](http://www.example.com$1) [R=301]
```

在 Nginx 中，只需要这样做:

```
server {
 server_name example.com;
 return 301 [http://www.example.com$request_uri;](http://www.example.com$request_uri;)
}
```

这就是全部了！

# 但是安全性呢？

![](img/84c8c53429833b7e48acfe6537a52306.png)

正如你们中的一些人在评论中指出的(谢谢！)，当您决定使用非 www 类型的 URL 时，会有一些安全问题。

如果你在子域名上运行各种不同的服务，你就要冒在你的主非 www 主页和所述服务之间共享 cookies 的风险。如果某些敏感数据存储在您不想与第三方共享的 cookies 中，这可能是一件坏事。

关于 cookies 和非 www 风格的 URL 还有一些其他的问题，你可以在这里阅读更多关于[的内容](https://www.bjornjohansen.no/www-or-not)