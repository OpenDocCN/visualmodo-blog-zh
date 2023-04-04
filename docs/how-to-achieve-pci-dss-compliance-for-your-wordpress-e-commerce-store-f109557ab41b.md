# 如何使你的 WordPress 电子商务商店符合 PCI DSS 标准

> 原文：<https://medium.com/visualmodo/how-to-achieve-pci-dss-compliance-for-your-wordpress-e-commerce-store-f109557ab41b?source=collection_archive---------0----------------------->

在 WordPress 上建立你的电子商务业务后，想到你的利润和销售额是令人兴奋的。然而，你的生意可能很快一落千丈，主要是如果你接受信用卡没有正确的合规。鉴于网上商店的性质，你可能会在你的业务中使用信用卡支付。为确保保护您的客户和业务，请查看 PCI DSS 合规性。在这篇权威性的文章中，我们深入探讨了 WordPress 电子商务网站和 PCI DSS 合规性之间的关系，以及如何实现平稳的业务运营合规性。

# 什么是 PCI DSS 合规性？

![](img/cb643947b42b27787b21b6b67a78715a.png)

PCI DSS 标准或支付卡行业数据安全标准是一项旨在确保信用卡信息安全的法规，尤其是在网络世界中。即使你只接受通过 Stripe 和 PayPal 账户的支付，你的 WordPress 电子商务商店也应该是合规的。所有商户，无论规模和交易，只要接受、处理、存储或传输卡数据，都需要遵守 PCI DSS。想象一下你的车里有安全带。即使没有人强迫你戴上它，不遵守的严重后果也是适用的。

支付卡行业安全标准委员会(PCI SSC)负责监管合规性法规。该组织由五大信用卡公司组成:Visa、Mastercard、JCB、Discover 和 American Express。该委员会成立于 2006 年 9 月 7 日，旨在保护信用卡信息并提高在线支付的安全性。

# WordPress 电子商务网站的 PCI DSS 合规性

幸运的是，由于大多数 WordPress 商店使用 PayPal 和 stripe 等第三方电子支付系统，合规过程比平时更短。然而，如果你选择扩大或改变你的业务性质，了解这些规定以及它们如何适用于你是有好处的。作为一个 WordPress 电子商务商店经营者，完成自我评估问卷(SAQ)就足够了。

# PCI DSS 合规性的商户级别是什么？

PCI DSS 标准为商家列出了四个级别。

*   1:每年超过 600 万笔卡交易。
*   每年 2:100 万到 600 万的卡交易。
*   3:每年 2 万到 100 万的卡交易量。
*   4:每年不到 2 万笔卡交易。

虽然这些级别适用于所有交易，但美国运通、JCB 和 Discover 还有其他要求。确定合规级别后，可以采取 SAQ。

# 什么是 PCI DSS SAQ？

SAQ 是一个验证文件，帮助你作为一个商人检查你的合规性。根据您处理付款的方式，有几种格式可供选择。完成 SAQ 后，您还应该填写合规证明。对于这一步，专家的支持至关重要，他可以带你完成正确的问卷，并确保你遵守所有阶段。

# WordPress 站点的 PCI DSS 需求是什么

PCI SSC 发布了最新版本——PCI DSS 3.2，取代了 3.1 版。该文件于 2018 年 1 月生效，尽管已经计划发布 4.0 版。作为商家，关注最新标准以确保合规是至关重要的。然而，目前我们主要关注当前可用的 3.2 版本。

PCI DSS 有 12 项要求，分属 6 个目标，如下所述。

# 建立和维护安全的网络和系统。

*   安装保护持卡人信息的防火墙。
*   更改软件、设备和系统的所有默认密码。

# 保护持卡人数据符合电子商务的 PCI DSS 要求

*   持卡人数据的保护。
*   加密公共网络上的持卡人数据。

# 拥有漏洞管理计划

*   定期更新软件和防病毒软件，保护您的系统免受恶意软件侵害。
*   开发和维护安全的系统和软件。

# 访问控制

*   将对持卡人数据的访问限制在需要知道的范围内。
*   使用识别和认证措施来控制访问。
*   控制对持卡人数据的物理访问。

# 监控和测试

*   跟踪和监控持卡人信息的所有网络访问。
*   对系统进行定期测试和筛选。

# 信息安全政策

*   维护一项安全政策，其中包括保护持卡人数据的所有措施。

# 维护符合 PCI DSS 的网站

PCI DSS 标准是所有处理信用卡数据的企业的通用标准。因此，了解如何为你的 WordPress 电子商务商店实现合规性是很重要的。更重要的是，不同的 WordPress 商店使用的方法可能不同，所以复制粘贴的方法可能行不通。

# 要求 1:安装保护持卡人信息的防火墙。

防火墙在你的网站和访问者之间起着屏障的作用。为您的网站配置防火墙时，有几个问题需要考虑。首先，您需要识别所有与您的网站交互的服务器、网络设备和服务。有了一个全面的列表，您可以确定哪里需要防火墙。

其次，在为各种设备配置防火墙时，您需要阻止传入和传出，以帮助您只允许必要的内容。一旦设置了防火墙，但不确定是否应该允许用户和服务进入，首先要做研究。你应该始终确保你的网站上允许的任何访问。最后，记住记录您的所有配置，并不断更新它们。

# 要求 2:更改软件、设备和系统的所有默认密码。

许多商家错误地依赖供应商提供的安全密码。然而，你应该总是改变所有产品的默认密码，不管你是否在 WordPress 上使用它们。

除了更改密码，隔离您的服务也是明智的。例如，您可以购买和托管您的域名，设置您的域名系统，托管您的网站，设置和托管电子邮件服务，并在不同的服务提供商上托管您的测试。

将你的插件限制在重要的插件上也很重要。选择插件时，一定要检查它们的来源，只使用值得信赖的。如果你有任何不必要的插件和主题，立即禁用并删除它们。最后，在安装了与您的网站兼容的任何硬件和软件之后，从制造商或您的安全提供商(如果有的话)那里了解如何加强它们的安全性。

# 要求 3:保护持卡人数据。

如果你经营电商店铺，你最有可能依赖的是 Stripe、PayPal 等第三方支付网关；这一步可能不适用于您的业务。但是，如果您手动处理付款信息，请务必记住:

*   千万不要手动记下付款信息。而是将数据直接输入支付网关。
*   只存储你需要的持卡人信息，删除你不需要的。
*   告知处理持卡人信息的人员错误处理数据的后果。

# 要求 4:加密公共网络上的持卡人数据。

首先，在你的 WordPress 站点上安装一个 SSL/TLS 证书，这样它就可以通过 HTTPS 访问了。幸运的是，许多网站都提供免费证书。一旦证书启动并运行，访问者和网站之间的所有数据都将被加密。

然而，即使你通过 HTTPS 访问持卡人数据，也要确保你的连接是完全安全的。例如，当使用开放的公共 WiFi 时，WordPress 网站总是使用 VPN。VPN 对你的在线活动进行加密，保护你免受公共连接上的窃听。它通过屏蔽你的私人信息来做到这一点，比如 IP 地址、搜索历史和位置。因此，电子商务的一个重要的 PCI DSS 合规性。

# 要求 5:定期更新软件和防病毒软件，保护您的系统免受恶意软件攻击。

这一步可以确保您的网站不容易受到攻击，也可以防止恶意软件。请务必从您的软件提供商那里安装最新的更新。保持你的防病毒软件、反恶意软件、防火墙和任何其他你在与你的 WordPress 网站交互的设备上使用的软件是最新的。恶意软件也是软件，通常，攻击者也会更新他们的恶意软件，以确保它是有用的。更新您的系统是保护您免受新威胁的最佳方式。

# 要求 6:开发和维护安全的系统和软件。

在这一步，你作为商家的角色是确保你为你的 WordPress 站点使用安全的软件和应用程序。下载软件和应用程序时，确保从值得信赖的商店下载，因为他们在向公众开放应用程序之前会预先批准应用程序。对于软件，只使用可信的和认可的供应商。供应商或开发商还应该拥有所有相关的经营许可证。

请记住，软件和应用程序开发人员发布的任何更新一经发布，就要立即安装。随着你的网站的发展，记住要验证任何新软件的来源。在购买之前，先看看关于该软件的评论和意见。安装后，请记住更改所有默认设置和密码，并使用供应商建议来提高安全性。

# 要求 7:将对持卡人数据的访问限制在需要知道的范围内。

确保您管理对网站的访问。最好的方法是利用“全部拒绝”功能，然后在检查时允许每个用户、操作系统、在线服务和网络组件访问。授予访问权限时，尤其是授予新用户访问权限时，请确保研究他们的来源和安全性，并确定他们为什么需要访问您的网站。因此，电子商务的一个重要的 PCI DSS 合规性。

# 要求 8:使用识别和认证措施来控制访问。

专注于利用认证措施，以确保只有真正的用户有权访问您的网站和持卡人数据。您可以为管理控制和帐户页面设置双因素身份验证(2FA)。还记得使用强密码，并教育您的用户需要强密码。您可以安装密码管理器来存储您的唯一密码，并配置强制用户为其门户创建强密码的策略。

您还应该使用唯一的凭据来验证每个用户的身份。有了针对您的网站、管理控制、客户端门户、网络设备和业务数据的唯一凭据，您还可以跟踪和接收任何尝试登录的警报。

# 要求 9:控制对持卡人数据的物理访问。

限制对笔记本电脑、智能手机、服务器和网络中任何其他设备的所有访问。首先，不允许随机用户访问您的商务 WiFi 和工作设备。如果你在实体办公室工作，安装合适的锁，不要让访客随意走动。最后，永远记住销毁密码和持卡人数据的所有实物证据。

# 要求 10:跟踪和监控持卡人信息的所有网络访问。

将你所有活动的审计历史记录保存至少一年，随时准备分析。您存储这些信息不仅是为了合规，也是为了帮助您管理网站的安全性。安装路由器等新设备时，记得打开它们的日志记录功能，以帮助您跟踪它们的活动。你也可以找到 WordPress 插件来跟踪你的所有活动。

# 要求 11 电子商务的 PCI DSS 合规性:对系统进行定期测试和筛选。

信息安全控制从来都不是一次性的活动。您需要持续监控您的安全系统的漏洞，并安装新的更新来提高安全性。你还需要为你的网络和服务器设置渗透测试，进行外围网络扫描，要求内部漏洞扫描，并使用 [WordPress 漏洞](https://visualmodo.com/vulnerabilities-in-wordpress-plugins-a-terrifying-trend/)扫描。引入 IDS 或 IPS 解决方案来帮助您检查和防止可能的黑客攻击也是至关重要的。有了正确的插件，你可以确保你的网站总是被筛选。

更新您的 It 库存以确保检查也很重要。如果没有这个列表，很容易会有没有合适的安全补丁的软件和插件在后台运行。保留一个更新的列表，以便您可以跟踪需要更新或卸载的内容。

# 要求 12:维护一个安全策略，包括保护持卡人数据的所有措施。

这个需求主要是记录在你的 WordPress 商店中加强安全性所需的所有步骤。一旦确定了维护安全所需的措施，就要记录下来，并分发给相关用户。确保您的政策清楚地概述了每个人在确保安全方面的角色以及不遵守的后果。它还应该包括正确的方法来使用设备和其他技术为您的网站商店。您还应该确保为您的员工列出教育和认知计划。该策略还应包括风险评估，以确定所有威胁及其影响，以及针对数据泄露的事件响应计划。

# 不合规的风险是什么？

有几个不合规的风险。

# 电子商务的罚款和损失 PCI DSS 合规

信用卡公司每个月都会对你处以 5000 到 100000 美元不等的罚款。这些罚款根据您的电子商务商店的交易量而有所不同。这些量还决定了您的业务应该达到什么级别的合规性。

对于任何企业来说，不遵从和违规造成的经济损失都是巨大的。重要的是要注意，首先，更换和发行信用卡的成本是每个与你的电子商务商店交易的客户 3-5 美元。即使解决了这个问题，银行和支付处理商也可能会提高收费。受影响的品牌也可能为了进一步保护消费者而转嫁监控所有被破坏的信用卡信息的成本。

# 支付禁令

相关的信用卡公司可以对你的业务加以限制，阻止它接受信用卡支付。如果您未能获得合规，信用卡品牌也可能会完全终止与您的业务的所有未来服务。

# 数据泄露

虽然 PCI DSS 合规性不能保护您的网站免受潜在数据泄露的影响，但它可以减轻泄露带来的打击。如果调查显示您采取了所有合规措施，信用卡品牌可能会选择降低或取消罚款。数据泄露可能导致收入损失，尤其是在客户对您的企业失去信任的情况下。在继续营业之前，你还必须花更多的钱来清理你的系统和升级安全性。

# 法医审计

如果你的企业遭到黑客攻击，你必须接受强制性的法庭审计。在此审计中，您需要提供 PCI DSS 文档以供检查，这样信用卡公司就可以确定数据泄露是否是您的违规行为造成的。首先，审计对你的企业来说是侵入性的和昂贵的，因为所有的费用都在你身上。其次，如果您不合规，取证审计员还会检查您的控制措施，以确定您的合规状态。

# 针对电子商务的法律诉讼 PCI DSS 合规

可能会有针对您的企业的集体诉讼，尤其是在数据泄露规模巨大的情况下。2007 年，TJX 面临大规模数据泄露，泄露了超过 4500 万张信用卡的详细信息。该公司透露，仅在违规 12 个月后，它就花费了超过 2.5 亿美元来弥补违规造成的损失，并赔偿受影响的银行和客户。

# 受损的商业信誉

暴露客户的信用卡信息足以让你对你的企业产生不信任，并通过差评毁掉你的品牌形象。客户也越来越难再次信任你，新客户也越来越难购物。