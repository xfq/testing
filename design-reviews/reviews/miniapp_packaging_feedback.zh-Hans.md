# MiniApp TAG Feedback Doc - 29 September 2022

简体中文翻译

如有任何争议，应以原始英文版本为权威版本。

# MiniApps TAG 反馈文档 - 2022年9月29日

英文原版：https://github.com/w3ctag/design-reviews/blob/main/reviews/miniapp_packaging_feedback.md

## 背景

2020年7月，W3C TAG就W3C MiniApp社区提出的三个TAG审阅请求发表了[一项声明](https://github.com/w3ctag/design-reviews/blob/main/reviews/miniapps_feedback.md)，这三个份文档分别是[MiniApp URI Scheme](https://github.com/w3ctag/design-reviews/issues/478)、[MiniApp Manifest](https://github.com/w3ctag/design-reviews/issues/524)和[MiniApp LifeCycle](https://github.com/w3ctag/design-reviews/issues/523)。TAG对这三份文档提出了反馈意见。对URI Scheme和Manifest的反馈也导致了对这些规范的实质性更改，这使TAG能够以积极的结果结束对这些文档的审阅。我们很高兴看到MiniApp提案与在相同领域的其他W3C工作相融合——这有助于构建One Web的目标。

TAG对Lifecycle文档的反馈尚未得到类似的更改。最近，我们收到了一份对MiniApp Packaging的审阅请求，该请求与Lifecycle相关，因为他们都指定了（Web）MiniApp如何被传输到设备上，并由用户安装和运行。

TAG的观点是，Web的安全模型有助于为所有Web用户提供一个安全可靠的平台，包括保护用户隐私和不法分子的攻击。随着Web在人们的生活中变得无处不在，并且随着Web的API和功能的增多，攻击表面也在增加，这些攻击和威胁也在增加。

作为最近的一个例子，我们想提请MiniApp社区关注最近关于嵌入webview组件的应用的安全模型的讨论，例如WebView 社区组中正在讨论的[注入自定义 JS 脚本](https://github.com/WebView-CG/usage-and-challenges/issues/36)和[应用可以使用WebView绕过Web安全标准、隐私标准和用户选择](https://github.com/WebView-CG/usage-and-challenges/issues/36)。

Web安全模型基于域（origin）的概念，这是Web的关键架构。随着Web变得越来越强大，这些强大的功能在安全的环境中运行变得越来越重要——也就是说，通过带有清晰的密码学来源链（证书颁发机构链）的 `https` 传输。因此，任何Web打包解决方案都必须保留域机制和安全上下文，以便从 Web 应用的角度来看，它可以在受信任的环境中运行。

此外，TAG担心zip格式的效率。

TAG指出，[HTTP signed exchanges](https://wicg.github.io/webpackage/draft-yasskin-http-origin-signed-responses.html)和[web bundles](https://wicg.github.io/webpackage/draft-yasskin-wpack-bundled-exchanges.html)的工作提供了一种解决方案，目前 WICG 社区组正在研究这种方法。TAG在该提案的早期积极审阅了这项工作，我们鼓励MiniApp小组在这里参与，看看bundles是否可以提供解决上述问题的替代方案。

## 提议

具体建议：MiniApp社区应研究使用保留域（origin）模型的打包解决方案。关于Lifecycle：MiniApp应用也应该在该安全模型中运行，保留 Web 的所有安全优势，同时还支持MiniApp社区设想的用例。Bundling和signed exchanges为实现这一结果提供了一条有希望的途径。市面上可能还有其他解决方案也可以解决这个问题。

## 参考资料

* [Minutes from discussion with Fuqiao](https://github.com/w3ctag/meetings/blob/gh-pages/2022/telcons/08-29-minutes.md#second-half--mini-app-discussion-with-guests-1)
* [Lifecycle](https://github.com/w3ctag/design-reviews/issues/523)
* [Packaging](https://github.com/w3ctag/design-reviews/issues/762)
* [2020 Miniapp feedback](https://github.com/w3ctag/design-reviews/blob/main/reviews/miniapps_feedback.md)