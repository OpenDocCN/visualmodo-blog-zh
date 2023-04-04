# WordPress 的 TypeScript 入门

> 原文：<https://medium.com/visualmodo/getting-started-with-typescript-for-wordpress-e605a05d8fbe?source=collection_archive---------0----------------------->

在这个软件开发时代，人们可以使用 JavaScript 开发几乎任何类型的应用程序。然而，JavaScript 的动态类型特性可能会引起大多数大型企业的关注，主要是因为它松散的类型检查特性。在本文中，你将学习如何开始使用 WordPress 的 TypeScript。

好消息是不需要等待静态系统被引入 JavaScript。您可以考虑改用 TypeScript。

![](img/f0cafb5661b48a0d1e70a1d0c50d2557.png)

JavaScript 不知道变量的数据类型，直到该变量在运行时被实例化。bug 经常被忽略，因为编写大型软件程序的开发人员倾向于将早期声明的变量重新赋值为不同类型的值，而不发出任何问题或警告。

在这篇文章中，你将了解到这个很好的选择——开始使用 WordPress 的 TypeScript 时你需要知道的定义和基本知识。

# 什么是 TypeScript？

TypeScript 是 JavaScript 的类型化超集。它编译成普通的 JavaScript。如果 JavaScript 是 CSS，那么 TypeScript 就是 SCSS。因此，本文中的“超集”意味着 TypeScript 作为一种语言包含了 JavaScript 的所有不同特性和功能，甚至更多。

当您编写任何有效的 JavaScript 代码时，它也是有效的类型脚本代码。TypeScript 还提供了编译成普通 JavaScript 和使用静态类型的最新特性。所有浏览器都支持它们。TypeScript 在解决问题或使 JavaScript 可伸缩方面做得非常好，这正是它的实际目标。

TypeScript 通过其接口、类和类型批注，使开发人员能够更好地控制他们的代码库。它基本上使开发人员不必手动修复恼人的控制台错误。

# 使用 TypeScript 的优势

以下是使用 TypeScript 的一些优点:

*   更简单的重构

尽管你想重构很多东西，但你对修改东西很谨慎，因为它们会触及许多其他文件和其他代码。当您使用 TypeScript 时，这将不再是一个问题，因为您已经可以通过单击集成开发环境(IDE)的“重命名符号”命令来重构它们。

使用 JavaScript 和其他动态类型语言同时重构多个文件的唯一方法是通过“搜索和替换”功能。这是使用正则表达式的传统方式。

然而，TypeScript(一种统计类型语言)中不再有“搜索和替换”功能。使用“重命名符号”和“查找所有出现”IDE 命令，您将能够看到应用程序中对象接口的给定属性、类或函数的所有出现。

TypeScript 不仅会帮助您找到所有重构位的实例。这也将有助于你在重命名它。重构后，如果代码中出现任何类型的不匹配，就会出现编译错误。

*   更少的错误

虽然不可能消除代码中的所有错误，但是可以使用 TypeScript 来减少它们。如果变量类型改变，在编译时检查类型后抛出错误。

对于开发人员来说，用类型管理他们的代码变得容易多了，因为他们可以找到明显但频繁出现的错误。

# WordPress 什么时候使用 TypeScript？

下列情况使使用 TypeScript 成为一个好主意:

*   假设你打算[开发一个网络应用](https://visualmodo.com/top-7-web-development-frameworks-in-2020/)或者建立一个网站并长期维护它。这是因为鼓励自我记录的代码；它有助于其他将要加入你的代码库的开发者更容易理解你的代码。
*   此外，如果你想创建一个库，可以考虑在里面写东西。使用您的库的开发人员将通过 TypeScript 的帮助从代码编辑那里获得适当类型的建议。

# 如何安装 WordPress 的类型脚本

您需要先安装它，然后才能开始编写出色的 TypeScript 代码。您可以在节点包管理器的帮助下安装 TypeScript。如果您还没有安装节点软件包管理器，您必须先安装它，然后再安装它。

您可以通过启动终端并运行以下命令来安装 TypeScript:NPM install-g TypeScript。

在您的终端中，运行 tsc-v 来检查安装后的版本。如果一切正常，您将在终端中看到脚本的版本号。

# 支持 WordPress 类型脚本的 ide 和文本编辑器

第一个支持 TypeScript 的 IDE 是 Visual Studio。好吧，既然微软创造了 TypeScript，那就不应该感到惊讶。

一旦它开始流行起来，越来越多的 ide 和编辑器通过插件或开箱即用的方式增加了对它的支持。具有内置支持的编辑器包括 Visual Studio Code，这是一个由微软创建的轻量级开源编辑器。对于开箱即用的支持，您可以查看 WebStorm。

为了便于开发，也可以使用插件。这些插件提供了各种各样的特性，比如语法高亮。

# 结论

本文旨在为开发人员提供一个简要的概述，包括它的不同特性以及如何安装它。还提供了关于用于开发的 ide 和文本编辑器的建议。当然，使用语言的好处是我们需要它。希望有足够的东西让懂 JavaScript 的开发者开始利用这种语言来提高他们对 WordPress 代码库稳定性的反应。

需要注意的是，使用 TypeScript 并非没有缺点。一个突出的缺点是复杂的打字系统。最后，你必须知道什么时候是使用这种语言的最佳时机，尤其是在 WordPress 上使用它的时候。