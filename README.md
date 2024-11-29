# 🤯 HEAD

> HTML `<head>` 元素的简易指南

[![Contributors](https://img.shields.io/github/contributors/joshbuchea/head.svg?style=for-the-badge)](https://github.com/joshbuchea/HEAD/graphs/contributors)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg?style=for-the-badge)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Follow @joshbuchea on Mastodon](https://img.shields.io/badge/Follow_@joshbuchea-purple?logo=mastodon&logoColor=white&style=for-the-badge)](https://hachyderm.io/@joshbuchea)

## 目录

- [推荐最低要求](#推荐最低要求)
- [元素](#元素)
- [Meta](#meta)
- [链接](#链接)
- [图标](#图标)
- [社交](#社交)
  - [Facebook Open Graph](#facebook-open-graph)
  - [Twitter 卡片](#twitter-卡片)
  - [Twitter 隐私](#twitter-隐私)
  - [Schema.org](#schemaorg)
  - [Pinterest](#pinterest)
  - [Facebook Instant Articles](#facebook-instant-articles)
  - [OEmbed](#oembed)
  - [QQ/Wechat](#qqwechat)
- [浏览器 / 平台](#浏览器--平台)
  - [Apple iOS](#apple-ios)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [中国浏览器](#中国浏览器)
  - [360 浏览器](#360-浏览器)
  - [QQ 移动浏览器](#qq-移动浏览器)
  - [UC 移动浏览器](#uc-移动浏览器)
- [应用链接](#应用链接)
- [其他资源](#其他资源)
- [相关项目](#相关项目)
- [其他格式](#其他格式)
- [🌐 翻译](#🌐-翻译)
- [协作](#协作)
  - [贡献者](#贡献者)
- [作者](#作者)
- [许可](#许可)

## 推荐最低要求

以下是任何网页文档（网站/应用）的基本要素：

```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!--
  上述两个 meta 标签 *必须* 放在 <head> 的最前面
  以确保文档正确渲染。
  任何其他 head 元素应放在这些标签之后。
 -->
<title>页面标题</title>
```

`meta charset` - 定义网站的编码，`utf-8` 是标准编码

`meta name="viewport"` - 与移动响应相关的视口设置

`width=device-width` - 使用设备的物理宽度（适用于移动设备）

`initial-scale=1` - 初始缩放比例，1 表示不缩放

**[⬆ 返回顶部](#目录)**

## 元素

有效的 `<head>` 元素包括 `meta`、`link`、`title`、`style`、`script`、`noscript` 和 `base`。

这些元素提供了关于文档如何被网页技术（例如浏览器、搜索引擎、机器人等）感知和渲染的信息。

```html
<!--
  设置此文档的字符编码，以便
  正确渲染 UTF-8 空间内的所有字符（如表情符号）。
-->
<meta charset="utf-8">

<!-- 设置文档的标题 -->
<title>页面标题</title>

<!-- 设置文档内所有相对 URL 的基础 URL -->
<base href="https://example.com/page.html">

<!-- 链接到外部 CSS 文件 -->
<link rel="stylesheet" href="styles.css">

<!-- 用于添加文档内的 CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript & No-JavaScript 标签 -->
<script src="script.js"></script>
<script>
  // 函数代码放这里
</script>
<noscript>
  <!-- 无 JS 替代内容 -->
</noscript>
```

**[⬆ 返回顶部](#目录)**

## Meta

```html
<!--
  以下两个 meta 标签 *必须* 放在 <head> 的最前面
  以确保文档正确渲染。
  任何其他 head 元素应放在这些标签之后。
-->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<!--
  控制资源的加载来源。
  尽早放置在 <head> 中，因为该标签
  仅适用于之后声明的资源。
-->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- Web 应用的名称（仅在网站作为应用使用时应使用） -->
<meta name="application-name" content="应用名称">

<!-- Chrome、Firefox OS 和 Opera 的主题颜色 -->
<meta name="theme-color" content="#4285f4">

<!-- 文档的简短描述（限制在 150 个字符内） -->
<!-- 此内容 *可能* 被用作搜索引擎结果的一部分。 -->
<meta name="description" content="页面描述">

<!-- 控制搜索引擎的爬取和索引行为 -->
<meta name="robots" content="index,follow"><!-- 所有搜索引擎 -->
<meta name="googlebot" content="index,follow"><!-- Google 特定 -->

<!-- 告诉 Google 不显示站点链接搜索框 -->
<meta name="google" content="nositelinkssearchbox">

<!-- 告诉 Google 不为此文档提供翻译 -->
<meta name="google" content="notranslate">

<!-- 验证网站所有权 -->
<meta name="google-site-verification" content="verification_token"><!-- Google 搜索控制台 -->
<meta name="yandex-verification" content="verification_token"><!-- Yandex 网站管理员 -->
<meta name="msvalidate.01" content="verification_token"><!-- Bing 网站管理员中心 -->
<meta name="alexaVerifyID" content="verification_token"><!-- Alexa 控制台 -->
<meta name="p:domain_verify" content="code_from_pinterest"><!-- Pinterest 控制台 -->
<meta name="norton-safeweb-site-verification" content="norton_code"><!-- Norton Safe Web -->

<!-- 识别用于构建文档的软件（例如 WordPress、Dreamweaver） -->
<meta name="generator" content="program">

<!-- 文档主题的简短描述 -->
<meta name="subject" content="文档主题">

<!-- 基于文档内容的总体年龄评级 -->
<meta name="rating" content="General">

<!-- 控制引用者信息的传递方式 -->
<meta name="referrer" content="no-referrer">

<!-- 禁用自动检测和格式化可能的电话号码 -->
<meta name="format-detection" content="telephone=no">

<!-- 通过设置为 "off" 完全选择退出 DNS 预获取 -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- 指定文档在特定框架中显示 -->
<meta http-equiv="Window-Target" content="_value">

<!-- 地理标签 -->
<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="country[-state]"><!-- 国家代码（ISO 3166-1）：必需，州代码（ISO 3166-2）：可选；例如 content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- 例如 content="New York City" -->

<!-- Web 货币化 https://webmonetization.org/docs/getting-started -->
<meta name="monetization" content="$paymentpointer.example">
```

- 📖 [Google 理解的 Meta 标签](https://support.google.com/webmasters/answer/79812?hl=zh)
- 📖 [WHATWG Wiki: MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions)
- 📖 [ICBM 在维基百科](https://zh.wikipedia.org/wiki/ICBM_address#Modern_use)
- 📖 [地理标记在维基百科](https://zh.wikipedia.org/wiki/Geotagging#HTML_pages)

**[⬆ 返回顶部](#目录)**

## 链接

```html
<!-- 指向外部样式表 -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- 有助于防止重复内容问题 -->
<link rel="canonical" href="https://example.com/article/?page=2">

<!-- 链接到当前文档的 AMP HTML 版本 -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">

<!-- 链接到指定 "安装" 凭证的 JSON 文件 -->
<link rel="manifest" href="manifest.json">

<!-- 链接到有关文档作者的信息 -->
<link rel="author" href="humans.txt">

<!-- 引用适用于链接上下文的版权声明 -->
<link rel="license" href="copyright.html">

<!-- 给出文档中可能使用其他语言的参考位置 -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- 提供有关作者或其他人的信息 -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- 链接到描述一组记录、文档或其他历史材料的文档 -->
<link rel="archives" href="https://example.com/archives/">

<!-- 链接到分层结构中的顶级资源 -->
<link rel="index" href="https://example.com/article/">

<!-- 提供自我引用 - 当文档有多个可能引用时非常有用 -->
<link rel="self" type="application/atom+xml" href="https://example.com/atom.xml">

<!-- 一系列文档中的第一个、最后一个、前一个和下一个文档 -->
<link rel="first" href="https://example.com/article/">
<link rel="last" href="https://example.com/article/?page=42">
<link rel="prev" href="https://example.com/article/?page=1">
<link rel="next" href="https://example.com/article/?page=3">

<!-- 当使用第三方服务来维护博客时使用 -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- 当另一个 WordPress 博客链接到您的 WordPress 博客或帖子时，形成自动评论 -->
<link rel="pingback" href="https://example.com/xmlrpc.php">

<!-- 在您的文档上链接时通知一个 URL -->
<link rel="webmention" href="https://example.com/webmention">

<!-- 允许使用 Micropub 客户端在您自己的域上发布 -->
<link rel="micropub" href="https://example.com/micropub">

<!-- Open Search -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="搜索标题">

<!-- Feed 订阅 -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- 预取、预加载、预浏览 -->
<!-- 更多信息: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="preload" href="image.png" as="image">
```

- 📖 [链接关系](https://www.iana.org/assignments/link-relations/link-relations.xhtml)

**[⬆ 返回顶部](#目录)**

## 图标

```html
<!-- 对于 IE 10 及以下版本 -->
<!-- 将 favicon.ico 放在根目录 - 无需标签 -->

<!-- 最高分辨率所需的图标 -->
<link rel="icon" sizes="192x192" href="/path/to/icon.png">

<!-- Apple 触控图标（重用 192px icon.png） -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- Safari 固定标签图标 -->
<link rel="mask-icon" href="/path/to/icon.svg" color="blue">
```

- 📖 [关于 Favicons（和触控图标）的全部内容](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- 📖 [创建固定标签图标](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/pinnedTabs/pinnedTabs.html)
- 📖 [Favicon 速查表](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [图标与浏览器颜色](https://developers.google.com/web/fundamentals/design-and-ux/browser-customization/)

**[⬆ 返回顶部](#目录)**

## 社交

### Facebook Open Graph
> 大多数内容以 URL 形式分享到 Facebook，因此在您的网站上标记 Open Graph 标签非常重要，以便控制您的内容在 Facebook 上的显示方式。 [更多关于 Facebook Open Graph 标记的信息](https://developers.facebook.com/docs/sharing/webmasters#markup) 

```html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="内容标题">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:image:alt" content="对图片内容的描述（不是标题）">
<meta property="og:description" content="描述内容">
<meta property="og:site_name" content="网站名称">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- 📖 [Open Graph 协议](http://ogp.me/)
- 🛠 使用 [Facebook 分享调试器](https://developers.facebook.com/tools/debug/) 测试您的页面

### Twitter 卡片
> 使用 Twitter 卡片，您可以在推文中附加丰富的照片、视频和媒体体验，帮助将流量引导到您的网站。 [更多关于 Twitter 卡片的信息](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards)

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="内容标题">
<meta name="twitter:description" content="内容描述，少于 200 个字符">
<meta name="twitter:image" content="https://example.com/image.jpg">
<meta name="twitter:image:alt" content="对图像的文字描述，传达图像的本质，适用于视障用户。最多 420 个字符。">
```

- 📖 [开始使用卡片 — Twitter 开发者](https://dev.twitter.com/cards/getting-started)
- 🛠 使用 [Twitter 卡片验证工具](https://cards-dev.twitter.com/validator) 测试您的页面

### Twitter 隐私
如果您在网站中嵌入推文，Twitter 可以使用您网站的信息为 Twitter 用户定制内容和建议。 [更多关于 Twitter 隐私选项的信息](https://dev.twitter.com/web/overview/privacy#what-privacy-options-do-website-publishers-have)。

```html
<!-- 禁止 Twitter 使用您网站的信息进行个性化内容推荐 -->
<meta name="twitter:dnt" content="on">
```

### Schema.org

```html
<html lang="" itemscope itemtype="https://schema.org/Article">
    <head>
      <link rel="author" href="">
      <link rel="publisher" href="">
      <meta itemprop="name" content="内容标题">
      <meta itemprop="description" content="内容描述，少于 200 个字符">
      <meta itemprop="image" content="https://example.com/image.jpg">
```

**注意：** 这些 meta 标签需要在 `<html>` 标签中添加 `itemscope` 和 `itemtype` 属性。

- 📖 [开始使用 - schema.org](https://schema.org/docs/gs.html)
- 🛠 使用 [丰富结果测试工具](https://search.google.com/test/rich-results) 测试您的页面

### Pinterest

Pinterest 允许您阻止人们从您的网站保存内容，根据他们的帮助中心说明。 `description` 是可选的。

```html
<meta name="pinterest" content="nopin" description="抱歉，您无法从我的网站保存内容！">
```

### Facebook Instant Articles

```html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- 文章的网页版本的 URL -->
<link rel="canonical" href="https://example.com/article.html">

<!-- 此文章使用的样式 -->
<meta property="fb:article_style" content="myarticlestyle">
```

- 📖 [创建文章 - Instant Articles](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- 📖 [代码示例 - Instant Articles](https://developers.facebook.com/docs/instant-articles/reference)

### OEmbed

```html
<link rel="alternate" type="application/json+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- 📖 [OEmbed 格式](https://oembed.com/)

### QQ/Wechat

用户将网页分享到 QQ WeChat 时会有格式化的消息

```html
<meta itemprop="name" content="分享标题">
<meta itemprop="image" content="http://imgcache.qq.com/qqshow/ac/v4/global/logo.png">
<meta name="description" itemprop="description" content="分享内容">
```
- 📖 [代码格式文档](http://open.mobile.qq.com/api/mqq/index#api:setShareInfo)

**[⬆ 返回顶部](#目录)**

## 浏览器 / 平台

### Apple iOS

```html
<!-- 智能应用横幅 -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- 禁用自动检测和格式化可能的电话号码 -->
<meta name="format-detection" content="telephone=no">

<!-- 启动画面图标（180x180px 或更大） -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- 启动画面图片 -->
<link rel="apple-touch-startup-image" href="/path/to/launch.png">

<!-- 启动画面图标标题 -->
<meta name="apple-mobile-web-app-title" content="应用标题">

<!-- 启用独立（全屏）模式 -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- 状态栏外观（仅在启用独立模式时有效） -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">

<!-- iOS 应用深度链接 -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- 📖 [配置 Web 应用程序](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

### Google Android

```html
<meta name="theme-color" content="#E64545">

<!-- 添加到主屏幕 -->
<meta name="mobile-web-app-capable" content="yes">
<!-- 更多信息: https://developer.chrome.com/multidevice/android/installtohomescreen -->

<!-- Android 应用深度链接 -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

### Google Chrome

```html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- 禁用翻译提示 -->
<meta name="google" content="notranslate">
```

### Microsoft Internet Explorer

```html
<!-- 强制 IE 8/9/10 使用其最新的渲染引擎 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">

<!-- 禁用 Skype 工具栏浏览器扩展的自动检测和格式化可能的电话号码 -->
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Windows 平铺 -->
<meta name="msapplication-config" content="/browserconfig.xml">
```

`browserconfig.xml` 的最低要求 XML 标记：

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

- 📖 [浏览器配置模式参考](https://msdn.microsoft.com/en-us/library/dn320426.aspx)

**[⬆ 返回顶部](#目录)**

## 中国浏览器

### 360 浏览器

```html
<!-- 选择渲染引擎顺序 -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ 移动浏览器

```html
<!-- 锁定屏幕为指定方向 -->
<meta name="x5-orientation" content="landscape/portrait">

<!-- 全屏显示此文档 -->
<meta name="x5-fullscreen" content="true">

<!-- 文档将以“应用模式”显示（全屏等） -->
<meta name="x5-page-mode" content="app">
```

### UC 移动浏览器

```html
<!-- 锁定屏幕为指定方向 -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- 全屏显示此文档 -->
<meta name="full-screen" content="yes">

<!-- UC 浏览器将在“文本模式”下显示图像 -->
<meta name="imagemode" content="force">

<!-- 文档将以“应用模式”显示（全屏、禁止手势等） -->
<meta name="browsermode" content="application">

<!-- 禁用 UC 浏览器的“夜间模式” -->
<meta name="nightmode" content="disable">

<!-- 简化文档以减少数据传输 -->
<meta name="layoutmode" content="fitscreen">

<!-- 禁用 UC 浏览器在文档中“文字过多时自动放大字体”的功能 -->
<meta name="wap-font-scale" content="no">
```

- 📖 [UC 浏览器文档](https://www.uc.cn/download/UCBrowser_U3_API.doc)

**[⬆ 返回顶部](#目录)**

## 应用链接

```html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">

<!-- 网页回退 -->
<meta property="al:web:url" content="https://applinks.org/documentation">
```

- 📖 [应用链接](https://developers.facebook.com/docs/applinks)

**[⬆ 返回顶部](#目录)**

## 其他资源

- 📖 [HTML5 Boilerplate 文档：HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- 📖 [HTML5 Boilerplate 文档：扩展和自定义](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[⬆ 返回顶部](#目录)**

## 相关项目

- [Atom HTML Head Snippets](https://github.com/joshbuchea/atom-html-head-snippets) - Atom 编辑器的 `HEAD` 代码片段包
- [Sublime Text HTML Head Snippets](https://github.com/marcobiedermann/sublime-head-snippets) - Sublime Text 编辑器的 `HEAD` 代码片段包
- [head-it](https://github.com/hemanth/head-it) - `HEAD` 代码片段的 CLI 接口
- [vue-head](https://github.com/ktquez/vue-head) - 为 Vue.js 操作 `HEAD` 标签的元信息

**[⬆ 返回顶部](#目录)**

## 其他格式

- 📄 [PDF](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

**[⬆ 返回顶部](#目录)**

## 🌐 翻译

- 🇮🇩 [印度尼西亚语](https://github.com/rijdz/HEAD)
- 🇧🇷 [巴西葡萄牙语](https://github.com/Webschool-io/HEAD)
- 🇨🇳 [中文（简体）](https://github.com/Amery2010/HEAD)
- 🇩🇪 [德语](https://github.com/Shidigital/HEAD)
- 🇮🇹 [意大利语](https://github.com/Fakkio/HEAD)
- 🇯🇵 [日语](https://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- 🇰🇷 [韩语](https://github.com/Lutece/HEAD)
- 🇷🇺 [俄语/Русский](https://github.com/Konfuze/HEAD)
- 🇪🇸 [西班牙语](https://github.com/alvaroadlf/HEAD)
- 🇹🇷 [土耳其语/Türkçe](https://github.com/mkg0/HEAD)

**[⬆ 返回顶部](#目录)**

## 🤝 协作

**打开一个 issue 或者 pull request 来建议更改或添加内容。**

### 指南

**HEAD** 仓库包含两个分支：

#### 1. `master`

该分支包含在 [htmlhead.dev](https://htmlhead.dev/) 网站上展示的 `README.md` 文件。所有对指南内容的更改应在此文件中进行。

请按照以下步骤进行 pull request：

- 每次只修改一个标签，或一组相关标签
- 在属性中使用双引号
- 在自闭合元素中不要包含尾部斜杠 — HTML5 规范表明它们是可选的
- 考虑包含支持您更改的文档链接

#### 2. `gh-pages`

该分支负责 [htmlhead.dev](https://htmlhead.dev/) 网站。我们使用 [Jekyll](https://jekyllrb.com/) 将 `README.md` markdown 文件部署到 [GitHub Pages](https://pages.github.com/)。所有与网站相关的修改应在此分支中进行。

在操作此分支之前，您可能需要查看 [Jekyll 文档](https://jekyllrb.com/docs/home/) 并了解 Jekyll 的工作方式。

## 贡献者

查看所有超赞的 [贡献者](https://github.com/joshbuchea/HEAD/graphs/contributors) 🤩

## 作者

**Josh Buchea**

- GitHub: [@joshbuchea](https://github.com/joshbuchea)
- Mastodon: [@joshbuchea@hachyderm.io](https://hachyderm.io/@joshbuchea)

## 💛 支持

如果这个项目对您或您的组织有帮助，请考虑直接支持我的工作：

- 💛 [在 GitHub 上赞助我](https://github.com/sponsors/joshbuchea)
- ⭐️ [在 GitHub 上为这个项目加星](https://github.com/joshbuchea/HEAD)
- 🐙 [在 GitHub 上关注我](https://github.com/joshbuchea)
- 🐘 [在 Mastodon 上关注我](https://hachyderm.io/@joshbuchea)

任何形式的支持都很有帮助，谢谢！ 🙏

— Josh

## 📝 许可

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ 返回顶部](#目录)**