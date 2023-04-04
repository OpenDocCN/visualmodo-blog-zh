# 如何在 WordPress 文章中添加元数据

> 原文：<https://medium.com/visualmodo/how-to-add-metadata-in-wordpress-posts-69bf713760de?source=collection_archive---------0----------------------->

你想学习如何在 WordPress 博客文章中显示文章元数据吗？文章元数据是关于你的博客文章的相关信息，如发表日期、类别、作者姓名等。在这篇文章中，我们将向你展示如何在 WordPress 文章中显示文章元数据。

# Post 元数据代表什么？

![](img/e4f6f4772a2383d2ea9601ddc905641c.png)

首先，post 元数据部分包含一篇博客文章的相关信息，比如发表日期、作者姓名、类别、标签和定制分类法等。其次，如果你有一个博客，那么你应该确保你的帖子的元数据是正确的，因为这些信息可以帮助访问者了解更多关于帖子的信息，也可以通过使你的网站更容易导航来帮助增加你的页面浏览量。

# 如何在 WordPress 中显示帖子元数据？

发布元数据的位置因主题而异。有些可能显示在文章标题之前，有些显示在标题之后，有些显示在内容之后。然而，太多的帖子会弄乱布局。理想的情况是只显示你认为必要的信息。现在让我们看看如何定制和添加 post meta。

# 自定义帖子元数据

如前所述，帖子的位置因主题而异。这里我们将处理一个特定的主题——在本例中，默认的 TwentySeventeen 主题，所以请记住代码和页面可能与您的主题不同。

在现代主题中，post meta 是在模板标签页中定义的，需要时会被调用，但是在一些主题中，你可能会发现 post meta 直接放在 post title 的前面或后面。一般来说，你会在 index.php 的、、*、*和*内容模板*页面中找到帖子元标签。一个简单的代码应该是这样的:

# 发布于

```
<?php the_time('F jS, Y'); ?> by <?php the_author_posts_link(); ?> <?php edit_post_link(); ?>
```

这段代码将显示类似于作者姓名在日期上发布的*的内容，并带有编辑按钮(仅当您登录仪表板时)。然而，现在大多数现代主题都使用模板标签页面来处理 post meta。让我们看看它是如何工作的。首先，在进行任何更改之前，您必须创建一个子主题。*

我们将在一个单一的职位网页上工作，这是它从前端看起来。假设我们想在作者的名字前添加一个用户图标，这样做如下:在 217 主题中，*一个 single.php*模板用于显示一篇文章。现在查找 get_template_part，注意那里的模板路径，在我们的例子中，路径是:

```
get_template_part( 'template-parts/post/content', get_post_format() );
```

# Content.php

现在根据路径打开*content.php*并搜索*条目-标题*部分。

```
<header class="entry-header"><?phpif ( 'post' === get_post_type() ) {echo '<div class="entry-meta">';if ( is_single() ) {twentyseventeen_posted_on();} else {echo twentyseventeen_time_link();twentyseventeen_edit_link();};echo '</div><!-- .entry-meta -->';};if ( is_single() ) {the_title( '<h1 class="entry-title">', '</h1>' );} elseif ( is_front_page() && is_home() ) {the_title( '<h3 class="entry-title"><a href="' . esc_url( get_permalink() ) . '" rel="bookmark">', '</a></h3>' );} else {the_title( '<h2 class="entry-title"><a href="' . esc_url( get_permalink() ) . '" rel="bookmark">', '</a></h2>' );}?></header><!-- .entry-header -->
```

我们可以看到 twenty Tencent _ posted _ on()；函数在这里被调用来显示文章元数据，我们必须编辑这个文章元数据函数。你会在 template-tags.php 的文件中找到这个函数。提示:检查主题的 function.php*文件以获得文件名和路径。*

搜索 twentyseventeen _ posted _ on()并将整个函数复制粘贴到您的子主题的 function.php 文件中(如果您的子主题中没有 function.php*文件，则创建一个同名的空白文件)。*

我们将在这里使用字体牛逼图标，在 WordPress 中使用字体牛逼最简单的方法是安装更好的字体牛逼插件。

```
if ( ! function_exists( 'twentyseventeen_posted_on' ) ) :/*** Prints HTML with meta information for the current post-date/time and author.*/function twentyseventeen_posted_on() {// Get the author name; wrap it in a link.$byline = sprintf(/* translators: %s: post author */__( 'by %s', 'twentyseventeen' ),'<span class="author vcard"><a class="url fn n" href="' . esc_url( get_author_posts_url( get_the_author_meta( 'ID' ) ) ) . '"><i class="fa fa-user" aria-hidden="true"></i>' . get_the_author() . '</a></span>');// Finally, let's write all of this to the page.echo '<span class="posted-on">' . twentyseventeen_time_link() . '</span><span class="byline"> ' . $byline . '</span>';}endif;
```

现在你可以在作者的名字旁边看到一个用户图标。提示:你可以直接在*content.php*文件中做这些修改，但是遵循主题结构是一个很好的实践。

# 添加帖子元数据

到目前为止，我们已经自定义现有的元标签。现在来收拾一下。假设我们想在文章标题后显示类别和标签。为此，从父主题中复制*content.php*文件并粘贴到您的子主题中，保持相同的目录模式。二十七子>模板-零件>岗位>content.php 到二十七子>模板-零件>岗位>content.php

现在你必须写一个新的函数。觉得很难吗？实际上不是，这是你需要做的。大多数主题会在文章的某个地方显示类别和标签，你只需要找到文件并在你的函数中复制代码就行了。

在我们的例子中，217 个主题类别和标签被放在内容之后。现在我们需要遵循我们之前的工作流程。首先，打开*content.php*，看看哪个函数用于类别和标签来编辑 WordPress 帖子元数据

# 代码示例

> 这里是 twentyseventeen _ entry _ footer()。现在转到 template-tags.php 文件，搜索 twentyseventeen _ entry _ footer()。如果(！function _ exists(' twenty Tencent _ entry _ footer '):/* * *打印包含类别、标签和注释的元信息的 HTML。*/function twenty seven _ entry _ footer(){/* translators:用于列表项之间，逗号*/ $separate_meta = __('，'，' twenty seven ')后有一个空格；//获取文章的类别。$ categories _ list = get _ the _ category _ list($ separate _ meta)；//获取帖子的标签。$tags_list = get_the_tag_list('，$ separate _ meta)；//我们不想输出。如果它是空的，请确保它不是空的。if(((twenty seventeen _ categorized _ blog()& & $ categories _ list)| | $ tags _ list)| | get _ edit _ post _ link()){ echo '
> 
> '；if(' post ' = = = get _ post _ type()){ if(($ categories _ list & & twenty seventeen _ categorized _ blog())| | $ tags _ list){ echo ''；//在显示之前，请确保有多个类别。if(＄categories _ list & & twenty seventeen _ categorized _ blog()){ echo ''。twenty seven _ get _ SVG(array(' icon ' = > ' folder-open '))。’。__('类别'，'第二十七')。’。$categories_list。’；} if(＄tags _ list){ echo ''。twenty seven _ get _ SVG(array(' icon ' = > ' hashtag '))。’。__( 'Tags '，' twentyseventeen ')。’。$tags_list。’；} echo ''；} } twenty seven _ edit _ link()；回声'

# Find the Code for Category and Tags

Finally, copy and paste the code for WordPress post meta data in your child theme’s function.php file within a new function, like this –

> if ( ! function_exists( ‘twentyseventeen_post_meta’ ) ) : /** * Prints HTML with meta information for the current post-date/time and author. */ function twentyseventeen_post_meta() { /* translators: used between list items, there is a space after the comma */ $separate_meta = __( ‘, ‘, ‘twentyseventeen’ ); // Get Categories for posts. $categories_list = get_the_category_list( $separate_meta ); // Get Tags for posts. $tags_list = get_the_tag_list( ‘’, $separate_meta ); echo ‘'；//在显示之前，请确保有多个类别。if(＄categories _ list & & twenty seventeen _ categorized _ blog()){ echo '*'。__('类别'，'第二十七')。’。$categories_list。**’；} if(＄tags _ list){ echo '*'。__( 'Tags '，' twentyseventeen ')。’。$tags_list。**’；} echo '****'；};endif**

## **定制 WordPress 文章元数据**

**既然我们已经将 meta 标签放在了我们想要的位置，那么是时候调整一些样式了。如果你知道 CSS 的基础知识，这是非常简单的。让我们调整我们的类别和标签部分。**

> **。条目标题。猫标签链接{ font-size:14px；} .条目标题。cat-links { padding-right:5px；}**

**所以，现在看起来不一样了。但是如果你想显示你自己的自定义图标，而不是字体-awesome 或任何其他，那么你可以使用你的图像作为 CSS 中的背景图像，如下所示:**

> **。条目标题。cat-links { background:URL(category-img . jpg)左中无重复；左填充:5px 填充-右:5px} .条目标题。tags-links { background:URL(tag-img . jpg)左中无重复；左填充:5px 填充-右:5px}**

**一旦完成，不要忘记从你的*function.php*文件中删除字体代码。**

# **如何删除 WordPress 中的帖子元数据？**

**删除任何帖子元非常简单，只需找到代码并删除它。例如，如果您现在看到我们的单个帖子页面，类别和标签现在出现在两个部分中。如果您不想在内容之后显示它，那么只需从 twentyseventeen _ entry _ footer()函数中删除类别和标记代码。所以新代码在你的孩子主题中应该是这样的。**

> **如果(！function _ exists(' twenty Tencent _ entry _ footer '):/* * *打印包含类别、标签和注释的元信息的 HTML。*/function twenty seventeen _ entry _ footer(){//我们不想输出。如果它是空的，请确保它不是空的。if(get _ edit _ post _ link()){ echo '**
> 
> **'；twenty seven _ edit _ link()；回声'**