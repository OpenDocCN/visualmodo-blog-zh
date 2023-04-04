# 使用 AJAX 让你的 WordPress 插件具有响应性

> 原文：<https://medium.com/visualmodo/making-your-wordpress-plugin-responsive-by-using-ajax-bb361f46faff?source=collection_archive---------0----------------------->

由于 AJAX 有许多吸引人的特性，它已经开始主宰 web 开发世界。它可以处理数据库操作，获取和显示请求的信息，而无需刷新整个网页。在这篇文章中，你将学习如何使用 AJAX 使你的 WordPress 插件具有响应性。

![](img/e12591ea2868e6d5cdd8f84315de9944.png)

这种动态 web 开发技术以闪电般的速度显示内容。它的速度使 AJAX 成为网站功能的流行选择，例如:

*   发表评论，
*   上传图片，
*   喜欢帖子等。

您甚至可以更进一步，通过 AJAX 开发整个网站。鉴于 AJAX 的流行，最大的 CMS 平台在其架构中包含 AJAX 也就不足为奇了。WordPress 就是这样一个 CMS 平台。

由于 AJAX 是可访问的，专家建议你用这种语言编写你的 WordPress 插件。考虑到这一点，我们将教你如何使用 AJAX 创建响应插件。

# 合并脚本和文件

让我们逐步来看看这个:

## 1 创建一个基础

首先，创建一个基础。要构建 AJAX 插件，您需要创建合适的环境。您可以通过添加必要的脚本来帮助它工作。其次，在插件目录的 WordPress 安装中创建一个 *ajaxloadpost1* 目录。

在同一个部分，在插件的头部创建 ajaxloadpost1.php。此外，通过这样做，你将能够从插件列表中[激活你的插件](https://visualmodo.com/best-free-wordpress-search-plugins-list/)。

按照这个步骤，在 ajaxloadpost1.php 中添加以下代码:

1.  define('AJAXLOADPOSTURL '，WP_PLUGIN_URL)。"/".dirname(plugin _ basename(_ _ FILE _ _))；
2.  函数 ajaxloadpost 1 _ enqueue scripts(){
3.  WP _ enqueue _ script(' ajaxloadpost 1 '，ajaxloadpost1。'/js/ajaxloadpost.js '，array(' jquery ')；
4.  WP _ localize _ script(' ajaxloadpost 1 '，' ajaxloadpostajax '，array(' Ajax URL ' = > admin _ URL(' admin-Ajax . PHP '))；
5.  }
6.  add_action('wp_enqueue_scripts '，ajaxloadpost 1 _ enqueue scripts)；

*   定义 AJAX Load Post URL 变量

接下来，你需要定义 *AJAX load post URL 变量*，因为它在指向插件的 URL 时会很方便。

*   添加 AJAX Load Post _ enqueue 脚本

之后，继续添加 ajaxloadpost_enqueuescripts 到 WordPress 的 wp_enqueue_scripts。执行此操作将帮助您将所有脚本入队。

下一步应该是添加 JavaScript 文件 ajaxloadpost.js，可以在\ WP-content \ plugins \ ajaxloadpost 1 \ js \文件夹中找到它。

*   使用 AJAX 创建一个 JS 文件夹

现在，创建一个 JS 文件夹，并将 ajaxloadpost.js 文件放入其中。因此，不必担心正确的顺序。WordPress 将为您将文件/脚本排队。

*   添加 JS 变量

一旦创建了 JS 文件夹，就可以用 wp_localize_script 添加 JS 变量。

# 整合 AJAX 处理程序

现在，是时候插入 AJAX 处理程序了，它的功能是创建 WordPress 的 AJAX 调用。要执行此步骤，请遵循以下代码:

现在，是时候插入 AJAX 处理程序了，它的功能是创建 WordPress 的 AJAX 调用。要执行此步骤，请遵循以下代码:

1.  函数 ajaxloadpost_ajaxhandlers() {
2.  如果(！WP _ verify _ nonce($ _ POST[' nonce ']，" ajaxloadpost_nonce")) {
3.  exit("错误的现时")；
4.  }
5.  $ these results = "；
6.  $ content _ posted = get _ POST($ _ POST[' postid '])；
7.  $ these results = $ content _ posted-> post _ content；
8.  die($ these results)；
9.  }
10.  add _ action(' WP _ Ajax _ no priv _ ajaxloadpost _ Ajax handlers '，' ajaxloadpost _ Ajax handlers ')；
11.  add _ action(' WP _ Ajax _ ajaxloadpost_ajaxhandlers '，' Ajax load post _ Ajax handlers ')

上面给出的代码序列将实现两个结果:

1.  首先，它将创建有问题的帖子的帖子 ID，
2.  其次，它将创建 nonce。

通过这个代码序列，您将能够检查文章 ID 和 nonce 的有用性。一旦你完成了检查，代码将从$_POST 变量中获取文章。

随后，您将能够通过利用 API get_post 来访问任何帖子及其内容。在 WordPress 中，你可以通过文章 ID 获得访问权限。

一旦 AJAX 处理程序功能就绪，您就可以在 WordPress 中注册该动作。这样，当您发出 AJAX 请求时，数据库可以获取适当的数据。

因此，要实现这一点，您需要以下列方式添加您的函数:

1.  add _ action(' WP _ Ajax _ no priv _ ajaxloadpost _ Ajax handlers '，' ajaxloadpost _ Ajax handlers ')；
2.  add _ action(' WP _ Ajax _ ajaxloadpost _ Ajax handlers '，' ajaxloadpost _ Ajax handlers ')；

到这一步结束时，您已经在 admin-ajax-php URL 中注册了所有正确的操作。此外，您将能够轻松地向 WordPress 发出 AJAX 请求。

# AJAX 和所需的 JavaScript

现在，编写 JS 代码，帮助 AJAX 通过 AJAX 处理程序获取适当的数据。因此，使用 AJAX 使 WordPress 插件响应的代码应该是这样的:

函数 ajaxloadpost_loadpost(postid，nonce) {

jQuery.ajax({

类型:' POST '，

url: ajaxloadpostajax1.ajaxurl，

数据:{

动作:' ajaxloadpost_ajaxhandlers '，

postid: postid，

现时:现时

},

成功:函数(data，textStatus，XMLHttpRequest) {

var loadpost result = ' # loadpost result '；

jQuery(loadpresult)。html(")；

jQuery(loadpresult)。追加(数据)；

},

错误:函数(MLHttpRequest，textStatus，errorThrown) {

alert(error thrown)；

这个代码实现了两个输入，即 nonce 和 post ID。然后，我们将利用 jQuery.ajax 函数创建一个对服务器的 AJAX 调用。因此，URL 将与 WordPress 的 admin-ajax.php 的 AJAX URL 相同。

此外，您可以在 JavaScript 变量中找到所需的 URL。如果您还记得，我们在将所需脚本入队时将它存储在那里。

按照这个步骤，用操作处理程序的名称指定操作。我们在注册 WordPress 时获得了操作处理程序的名称。您还需要随帖子 ID 一起发布 nonce。

如果您能够没有任何错误地实现它，那么您可以继续更新 id # loadpostreult

。这将通过我们的 AJAX 处理程序获取适当的内容。

# 展示文章列表:使用 AJAX 的 WordPress 插件响应

如果你已经达到这一点，没有任何错误。因此，您可以继续显示文章标题。显示帖子。最后，您需要输入相关代码，通过 AJAX 调用获取请求的内容。

以下是执行此步骤所需的一系列代码:

> 函数 ajaxloadpost _ show _ posts($ the number = ' 5 '){
> 
> $ our results = "；
> 
> $ Query = new WP _ Query(' posts _ per _ page = ')。$ the number)；
> 
> while ( $query->have_posts()):
> 
> $ query-> the _ post()；
> 
> $ nonce = WP _ create _ nonce(" ajaxloadpost _ nonce ")；
> 
> $args = get_the_ID()。",'".$nonce。'";
> 
> $ the link = '【T1]'。get_the_title()。’；
> 
> $我们的结果。= '
> 
> *   '。$thelink。’；
> 
> endwhile
> 
> WP _ reset _ postdata()；
> 
> $我们的结果。= '
> 
> '；
> 
> 返回$ ourresults
> 
> }
> 
> 函数 ajaxloadpost _ sc _ function($ atts){
> 
> 返回 ajaxloadpost _ show _ posts()；
> 
> }

add_shortcode( 'AJAXLOADPOST '，' AJAXLOADPOST _ sc _ function ')；

在第一组代码 ajaxloadpost_show_posts 中，您可以提交一个查询来获取最新的帖子。因此，你可以遍历最新的文章列表，并通过标签整合标题的名称。

它将通知 JavaScript Ajax load post _ load post 获取帖子 ID 和 nonce。而且，这个动作会创建一个空的。AJAX 处理程序的结果将填充这个空的。

此外，你还可以为每个网页创建一个简码。为此，您可以在页面上添加[AJAXLOADPOST]来查看标题列表。完成后，您的网页将包含最新帖子的标题列表。

# 外卖——通过几个简单的步骤，使用 AJAX 让你的 WordPress 插件响应迅速

从这个插件教程可以看出。另外，AJAX 并不难用。你可以轻松地将它整合到 WordPress 中。这使得 WordPress web 开发比以前容易多了。

如果你是新手，AJAX 可能听起来有点复杂。然而，一旦你明白了，它看起来和工作都很棒！

使用上面给出的步骤，你可以添加任何 AJAX 插件到你的 WordPress 站点。无论是 AJAX 页面加载器还是像活动日历这样的第三方插件。

通过这些步骤，用户可以点击并查看帖子，而不必加载整个网页。因此，如果您愿意，您可以通过在代码集中包含更多特性来定制代码集。

最后，我们希望这个教程足够清晰简单，便于你理解和练习。