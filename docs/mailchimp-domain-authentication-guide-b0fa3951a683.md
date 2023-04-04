# MailChimp 域认证指南

> 原文：<https://medium.com/visualmodo/mailchimp-domain-authentication-guide-b0fa3951a683?source=collection_archive---------0----------------------->

在本文中，您将了解如何设置 DKIM 并添加 MailChimp 域身份验证来保护您的电子邮件并使其正确发送。

Google、Yahoo 和 Microsoft 等互联网服务提供商(ISP)使用 DKIM 和 SPF 身份验证来扫描传入电子邮件中的垃圾邮件或欺骗地址。未通过认证的电子邮件更有可能到达垃圾邮件文件夹。

为了帮助确保您的活动到达收件人的收件箱，并使您的活动看起来更专业，您可以为您的域设置自定义 DKIM 身份验证，并将 MailChimp 域验证添加到您的 SPF 记录中。

在这篇文章中，我将向你展示如果你使用 [Cloudflare](https://www.cloudflare.com/) 和 [G Suite](https://gsuite.google.com/) ，如何在 MailChimp 中验证你的域名。验证您的域名是很重要的，因为您可以进一步防止您的新闻稿进入垃圾邮件文件夹。

# MailChimp 域认证指南

![](img/247db9dbece4c7617c14504d13d39e14.png)

如果它们变成了垃圾邮件，那么发送简讯还有什么意义呢？它还将取消默认的 MailChimp 认证信息(“via mcsv.net”或“代表 mcsv.net”)，这些信息可能会出现在一些电子邮件客户端中您的“发件人”姓名旁边。

这里有一个来自 MailChimp 的关于它在 Gmail 中的样子的例子:对于一些用户来说，它看起来很奇怪，甚至可疑，你不希望这样，对吗？因此，为了在 MailChimp 中验证您的域，您需要在您的域的 DNS 上设置 DKIM 和 SPF 记录。听起来比实际复杂，放心吧！

由于我正在使用 G 套件，并且我已经添加了来自谷歌的 DKIM 和 SPF 记录，我想知道是否也可以添加来自 [MailChimp](https://visualmodo.com/blog/) 的其他记录。因此，我做了一些调查，也联系了 G 套件支持，因为这不是我的专业领域，我发现在您的域名的 DNS 中添加额外的 DKIM 和 SPF 记录没有问题。

# 从 MailChimp 获取 DKIM 和 SPF 记录

1.  转到**账户**部分。
2.  从**设置**下拉菜单中点击**验证域**。
3.  点击**查看设置说明**链接。

我的站点已经认证过了，不过没关系；无论如何，你都会有那个链接。

让该选项卡保持打开状态，以便在登录 Cloudflare 时可以复制 DKIM 和 SPF 记录。

# 在 Cloudflare 中添加 MailChimp

登录到 Cloudflare 并访问 **DNS** 部分。

为 **DKIM** 创建一个 **CNAME** 记录。

*   从第一个下拉菜单中选择**CNAME**；
*   在**名称**字段中，从 MailChimp 复制**域密钥**并添加到那里。大概是这样的:`k1._domainkey.yourdomain.com`。不要抄这个！
*   在**域名**字段中，添加 **DKIM 值**，即`dkim.mcsv.net`；
*   **点击云图标**使其变灰，否则会报错，无法工作；
*   点击**添加记录**按钮。

请注意，在您添加记录后，您的域密钥中的`.yourdomain.com`部分不会显示出来，但是不要担心，它仍然存在。Cloudflare 只是隐藏它，而不是删除它。

将 **SPF 记录**添加到 G 套件记录的旁边。

如果您正在使用 G Suite，我假设您已经为它设置了一个 SPF 记录。如果没有，你真的应该去做！这是指南。

现在，与 DKIM 记录不同，您不会创建新的 SPF 记录。相反，您将把 MailChimp 中的一个添加到 G Suite 的旁边。

所以，找到 G Suite SPF 记录，点击它。

现在在 G 套件 SPF 记录后面加上这个:`include:servers.mcsv.net`。

我建议从你的 MailChimp 帐户复制一个，而不是这个，因为它将来可能会改变。

所以，**不要从 MailChimp 的说明:`v=spf1 include:servers.mcsv.net ?all`中添加整个 SPF 记录**。

如果没有添加任何 SPF 记录，您应该只添加整个记录，并且必须从头开始创建一个记录。

这是一个普遍的规则，不仅仅是在你使用 G 套件的时候。

您可能已经注意到 MailChimp 在 SPF 记录的末尾使用了`?all`，但是 G Suite 使用了`~all`。

不能添加两个版本，所以我决定保留 G Suite 的那个。

你可以在这里找到更多关于`~all`和`?all`以及其他版本[的信息。](http://www.openspf.org/SPF_Record_Syntax)

**第 4 步** —返回 MailChimp —在认证设置说明部分(见上文)—并按下**认证域**按钮。

就像上面说的，甚至可能需要 48 小时来传播 DNS 更改。通常情况下，需要的时间更少。

你现在应该都准备好了！

# 云闪中的 CNAME 变平

[据说](/yump-developer-blog/mailchimp-dkim-domain-verification-fails-with-cloudflare-cname-flattening-ef1332e1e97e)如果您在 Cloudflare 中启用了 CNAME 扁平化，MailChimp 域身份验证将无法工作，您将得到一个错误，而不是绿色复选标记。

我不知道这是固定的还是我只是运气好，但它对我来说工作得很好。

如果这对你不起作用，你必须在 Cloudflare 中禁用 CNAME 展平。你可以从你添加 DKIM 和 SPF 记录的地方向下滚动一点找到它。坏消息是，如果您至少使用 Cloudflare 的 Pro 计划，您将只有禁用选项可用。你不能在免费计划中禁用它。

因此，如果你已经拥有一个专业或更高的计划，然后禁用 CNAME 展平，按下 MailChimp 中的**认证域**按钮，然后重新激活 CNAME 展平。不幸的是，如果你使用免费计划，你将不得不购买专业计划来执行这个变通办法。希望它能像对我一样对你有用。

# 最后的话

希望你觉得这篇文章有用且全面，并且你成功地[在 MailChimp 中](https://visualmodo.com/wordpress-themes/)验证了你的域名！

别忘了分享帖子来帮助别人！如果您有任何问题或想法，请留言或通过联系人或评论部分发送消息。