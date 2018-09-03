# ![Markdown Intro](./assets/title.png)

自从 2014 年左右接触到 Markdown 以来，对它的使用就一发而不可收拾。从最开始使用它在 GitHub Pages 里写博客，到用它编辑项目的 README 文件，再到撰写开发文档，编辑微信公众号文章和邮件内容等等，这期间也见证了它在各类平台和网站上的普及和被原生支持，可以说，Markdown 如今已经渗透了我在技术和网络活动的方方面面，成为了我撰写文本文档的首选。

那么首先我们一起来看一下它的「定义」：

> Markdown 是一种轻量级标记语言，创始人为 John Gruber。它允许人们「使用易读易写的纯文本格式编写文档，然后转换成有效的 XHTML（或者 HTML）文档」。——维基百科

本文档的目的不在于面面俱到地介绍 Markdown，只是作为我对其理解的笔记整理，希望能同时帮助一些对 Markdown 感兴趣的人快速上手，或是作为一个工具，供对其已经有所了解的人在需要时参考。

接下来请随我一起深入了解这门并不神秘的实用标记语言。

# ![Table of Contents](./assets/toc.png)

<!-- vim-markdown-toc GFM -->

* [背景](#背景)
    * [优点](#优点)
    * [使用场景](#使用场景)
    * [编辑工具](#编辑工具)
* [语法](#语法)
    * [标题](#标题)
    * [段落](#段落)
    * [行内格式](#行内格式)
    * [引用块](#引用块)
    * [超链接](#超链接)
    * [图片](#图片)
    * [列表](#列表)
    * [代码块](#代码块)
    * [水平分割线](#水平分割线)
    * [嵌入 HTML](#嵌入-html)
* [扩展语法](#扩展语法)
    * [表格](#表格)
    * [任务列表](#任务列表)
    * [删除线](#删除线)
    * [自动链接](#自动链接)
* [奇技淫巧](#奇技淫巧)
    * [画流程图和时序图](#画流程图和时序图)
    * [用 Markdown 做 PPT](#用-markdown-做-ppt)
* [参考](#参考)

<!-- vim-markdown-toc -->

## 背景

### 优点

1. 专注于文字内容；

2. 纯文本，易读易写，可以方便地纳入版本控制；

3. 语法简单，没有什么学习成本，能轻松在码字的同时做出美观大方的排版。

### 使用场景

* 各类代码托管平台

    主流的代码托管平台，如 GitHub、GitLab、BitBucket、Coding、Gitee 等等，都支持 Markdown 语法，很多开源项目的 README、开发文档、帮助文档、Wiki 等都用 Markdown 写作。

* 技术社区和写作平台

    StackOverflow、CSDN、掘金、简书、GitBook

* 论坛

    V2EX、光谷社区

个人感觉比较遗憾的一点是各平台可能采用不同语言实现的 Markdown 解析引擎，或采用同一解析引擎的不同版本，而且可能有不同程度的定制与扩展，这导致在不同平台上使用 Markdown 写作时体验并不完全一致。

### 编辑工具

理论上任何一款文本编辑器都能用于编辑 Markdown 文档，它们分别提供了不同程度的语法高亮、预览等功能，以下只是列举其中一部分，选择自己称手的即可。

* 现代编辑器

    VSCode / Atom

* 传统编辑器

    Vim / Emacs / Sublime Text / Notepad++

* IDE 自带编辑器

    IntelliJ IDEA / Android Studio / WebStorm

* 专用编辑器

    Ulysses / Mou / Markpad

* 在线编辑器

    各种支持 Markdown 的网站都提供了在线编辑器

## 语法

### 标题

Markdown：

```
# atx-style 一级标题

## 二级标题

###### 六级标题

Setext-style 一级标题
===

二级标题
---
```

预览效果：

> # atx-style 一级标题
> 
> ## 二级标题
> 
> ###### 六级标题
>
> Setext-style 一级标题
> ===
>
> 二级标题
> ---

对应 HTML：

```html
<h1>atx-style 一级标题</h1>

<h2>二级标题</h2>

<h6>六级标题</h6>

<h1>Setext-style 一级标题</h1>

<h2>二级标题</h2>
```

### 段落

中间没有空行的连续不断的几行文字被视为一个段落。

Markdown：

```
白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）
```

预览效果：

白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）

对应 HTML：

```html
<p>白日依山尽，</p>

<p>黄河入海流。
（句号后面没有空格）</p>

<p>欲穷千里目，</p>

<p>
  更上一层楼。
  <br>
  （句号后面有俩空格）
</p>
```

### 行内格式

对段落或者部分文本的强调效果。

Markdown：

```
后面俩字**加黑**
后面俩字__加黑__

后面俩字*斜体*
后面俩字_斜体_
```

预览效果：

后面俩字**加黑**
后面俩字__加黑__

后面俩字*斜体*
后面俩字_斜体_

对应 HTML：

```html
<p>
  后面俩字
  <strong>加黑</strong>
  后面俩字
  <strong>加黑</strong>
</p>

<p>
  后面俩字
  <em>斜体</em>
  后面俩字
  <em>斜体</em>
</p>
```

### 引用块

Markdown：

```
> 引用块段落一。
>
> 引用块段落二。
>> 内嵌引用块段落一。
>
> ### 引用块内的标题
```

预览效果：

> 引用块段落一。
>
> 引用块段落二。
>
> > 内嵌引用块段落一。
>
> ### 引用块内的标题

对应 HTML：

```html
<blockquote>
  <p>引用块段落一。</p>
  <p>引用块段落二。</p>
  <blockquote>
    <p>内嵌引用块段落一。</p>
  </blockquote>
  <h3 id="引用块内的标题">引用块内的标题</h3>
</blockquote>
```

### 超链接

Markdown 支持行内式链接和引用式链接。

Markdown：

```
行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。

[1]: https://mazhuang.org
[2]: https://github.com/mzlogin "我的 GitHub 主页"
```

预览效果：

行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。

[1]: https://mazhuang.org
[2]: https://github.com/mzlogin "我的 GitHub 主页"

对应 HTML：

```html
<p>
  行内式&nbsp;
  <a href="https://mazhuang.org" title="我的个人博客">博客</a>
  &nbsp;链接，带 title。
</p>
<p>
  行内式&nbsp;
  <a href="https://github.com/mzlogin">GitHub</a>
  &nbsp;链接。
</p>
<p>
  引用式&nbsp;
  <a href="https://mazhuang.org">博客</a>
  &nbsp;链接。
</p>
<p>
  引用式&nbsp;
  <a href="https://github.com/mzlogin" title="我的 GitHub 主页">GitHub</a>
  &nbsp;链接，带 title。
</p>
```

### 图片

在超链接的写法前加一个 `!`，就是引用图片的方法。

Markdown：

```
![Alt text](https://mazhuang.org/favicon.ico "favicon")
```

预览效果：

![Alt text](https://mazhuang.org/favicon.ico "favicon")

对应 HTML：

```html
<img src="https://mazhuang.org/favicon.ico" alt="Alt text" title="favicon">
```

### 列表

包括有序列表和无序列表。

Markdown：

```
- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲
```

预览效果：

- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲

对应 HTML：

```html
<ul>
  <li>苹果</li>
  <li>葡萄</li>
  <li>榴莲</li>
</ul>
<ol>
  <li>苹果</li>
  <li>葡萄</li>
  <li>榴莲</li>
</ol>
```

其中无序列表的标记可以使用 `+`、`-` 或 `*`，有序列表前的数字可以是无序的。

### 代码块

支持行内代码和代码块。

Markdown：

    Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

    ```java
    if (TextUtils.isEmpty(text)) {
        return null;
    }
    ```

预览效果：

Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

```java
if (TextUtils.isEmpty(text)) {
    return null;
}
```

对应 HTML：

```html

```

### 水平分割线

使用一个单独行里的三个或以上 `*`、`-` 来生产一条水平分割线，它们之间可以有空格。

Markdown：

```
***

-----

- - -
```

预览效果：

> ***
> 
> -----
> 
> - - -

对应 HTML：

```
<hr />

<hr />

<hr />
```

### 嵌入 HTML

Markdown 标记语言的目的不是替代 HTML，也不是发明一种更便捷的插入 HTML 标签的方式。它所能产生的 HTML 标签只是 HTML 里的一个很小的子集。

对于那些没有办法用 Markdown 语法来对应的 HTML 标签，直接使用 HTML 来写就好了。

## 扩展语法

### 表格

### 任务列表

### 删除线

### 自动链接

## 奇技淫巧

### 画流程图和时序图

### 用 Markdown 做 PPT

## 参考

* [Markdown: Syntax - DARING FIREBALL](https://daringfireball.net/projects/markdown/syntax)
* [Markdown - 维基百科](https://zh.wikipedia.org/wiki/Markdown)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
