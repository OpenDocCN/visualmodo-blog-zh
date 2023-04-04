# WooCommerce 图像大小更改指南

> 原文：<https://medium.com/visualmodo/woocommerce-images-size-change-guide-15594ad870e?source=collection_archive---------0----------------------->

让我们面对现实吧，产品形象是销售背后至关重要的驱动力。3.3 中的 WooCommerce images 旨在通过对图像大小设置和图像渲染的一些改变来改善这一点。

WooCommerce 3.3 引入了新的图像裁剪设置。商店老板现在可以控制他们的主图像的宽度和高度，以及通过视觉提示来裁剪图像在前端的外观。除此之外，我们也给了主题更多的控制图片设置的支持，以确保产品图片开箱后看起来不错。

![](img/ee62946479d93e24f1dec5a36d8d2691.png)

那么现在在 WooCommerce 里怎么设置商品图片尺寸呢？现在可以在定制器下配置图像大小。进入外观>自定义> WooCommerce >产品图片。

您可以在这里设置主图像宽度、缩略图宽度和缩略图裁剪。图像高度已被有意移除，因为它们是根据您的设置自动计算的。这里值得注意的是，您的主要或“单一”产品图像不再有任何裁剪设置；他们将永远显示未剪辑。

一旦您对这些设置进行了任何更改，WooCommerce 将自动生成新的图像尺寸。这可能需要一点时间来处理，但它在后台运行。

如果你想查看背景再生的状态，你可以进入 WooCommerce > Status > Logs，从 wc-image-regeneration 开始的下拉列表中选择日志。

# 缺少尺寸

您可能会注意到定制器屏幕中缺少主图像宽度和缩略图宽度设置。

不要担心，如果你的主题声明了 WooCommerce [支持](https://visualmodo.com/blog/)并定义了这些设置，那么它们将从定制器中移除。WooCommerce 还打包了一些流行的主题支持声明，可以在 woo commerce/includes/theme-support/下找到。

# WooCommerce 图像大小

在你的孩子/【functions.php】定制主题中，或者在一个定制插件中，你可以使用下面的代码来移除主题支持并让选项在定制器中再次显示:

> /**
> *取消设置图像宽度主题支持。
> */
> 函数 iconic _ modify _ theme _ support(){
> $ theme _ support = get _ theme _ support(' woo commerce ')；
> $ theme _ support = is _ array($ theme _ support)？$ theme _ support[0]:array()；
> 
> unset($ theme _ support[' single _ image _ width ']，$ theme _ support[' thumbnail _ image _ width '])；
> 
> remove _ theme _ support(' woo commerce ')；
> add _ theme _ support(' woo commerce '，$ theme _ support)；
> }
> 
> add_action( 'after_setup_theme '，' iconic_modify_theme_support '，10)；

或者，您可以将这些值更改为其他值，如下所示:

> /**
> *修改图像宽度主题支持。
> */
> 函数 iconic _ modify _ theme _ support(){
> $ theme _ support = get _ theme _ support(' woo commerce ')；
> $ theme _ support = is _ array($ theme _ support)？$ theme _ support[0]:array()；
> 
> $ theme _ support[' single _ image _ width ']= 800；
> $ theme _ support[' thumbnail _ image _ width ']= 150；
> 
> remove _ theme _ support(' woo commerce ')；
> add _ theme _ support(' woo commerce '，$ theme _ support)；
> }
> 
> add_action( 'after_setup_theme '，' iconic_modify_theme_support '，10)；

如果您正在构建一个没有现有 WooCommerce 支持声明的自定义主题，您只需像这样添加支持:

> add_theme_support( 'woocommerce '，array(
> ' single _ image _ width ' =>800，
> ' thumbnail _ image _ width ' =>150，
> )；

在 WooCommerce 3.3+中，目录[图片](https://shots.visualmodo.com/)尺寸被移除。相反，目录使用与缩略图相同的设置。

可以通过编程来设置裁剪值。您可以像这样简单地运行 update_option()调用:

> update _ option(' woo commerce _ thumbnail _ cropping '，' 1:1 ')；

这些值可以是下列任意值:

*   不裁剪
    根本不裁剪缩略图。
*   1:1(任意比例)
    根据缩略图宽度和该比例裁剪图像。
*   自定义
    自定义也基于缩略图宽度，并附带两个其他选项:
*   woo commerce _ thumbnail _ cropping _ custom _ width
    一个宽度比例，例如 4。
*   woo commerce _ thumbnail _ cropping _ custom _ height
    一个高度比，比如 3。

例如，要将裁剪设定为自定，您可以这样做:

> update _ option(' woo commerce _ thumbnail _ cropping '，' custom ')；
> update _ option(' woo commerce _ thumbnail _ cropping _ custom _ width '，' 4 ')；
> update _ option(' woo commerce _ thumbnail _ cropping _ custom _ height '，' 3 ')；

注意:WooCommerce 会观察这些选项的变化，如果有变化，它会自动开始背景图像的重新生成过程。

# 最后的话

在 WooCommerce 中，图像尺寸的处理方式发生了一些变化，起初可能会让人感到困惑。我希望您现在了解如何处理这些变化，以及如何定制它们来满足您的需求。在我看来，最好的事情之一就是背景图像的再生。这样会节省用户很多时间和困惑！