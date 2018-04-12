---
title: "Learn Theme for Hugo"
---

# Hugo learn theme

[Hugo-theme-learn](http://github.com/matcornic/hugo-theme-learn) 是 [Hugo](https://gohugo.io/) 的一个主题。 Hugo 是快速且现代的静态网站引擎，使用 Go 语言实现。虽然 Hugo 经常用于搭建博客，但此主题则是**完全为搭建在线文档而设计**，且支持多语言。

此主题部分移植自 [Grav](https://getgrav.org/) 的 [Learn theme](http://learn.getgrav.org/)。Grav 是现代的基于文件的 CMS，使用 PHP 实现。

{{% notice tip %}}Learn theme 使用特殊的 _页面目录结构_ 组织内容，即：所有的内容都是页面，页面又可嵌套其他页面。[相关阅读]({{%relref "cont/pages/_index.md"%}})
{{% /notice %}}

## 主要特性

* [自动搜索]({{%relref "basics/configuration/_index.md#activate-search" %}})
* [多语言]({{%relref "cont/i18n/_index.md" %}})
* **无限目录层级**
* **自动翻页按钮，可遍历目录项目**
* [图片缩放, 自定义样式（阴影）...]({{%relref "cont/markdown.en.md#images" %}})
* [附件]({{%relref "shortcodes/attachments.en.md" %}})
* [子页面目录]({{%relref "shortcodes/children/_index.md" %}})
* [Mermaid 图表]({{%relref "shortcodes/mermaid.en.md" %}})（流程图，时序图，甘特图）
* [自定义外观、风格以及主题色]({{%relref "basics/style-customization/_index.md"%}})
* [按钮]({{%relref "shortcodes/button.en.md" %}})，[提示/笔记/通知/警告 的通知框]({{%relref "shortcodes/notice.en.md" %}})，[展开／收起]({{%relref "shortcodes/expand.en.md" %}})

![预览](https://github.com/matcornic/hugo-theme-learn/raw/master/images/screenshot.png?width=40pc&classes=shadow)

## 给此文档做贡献

只要点击每个页面右上角的 **编辑此页** 链接，即可自由地更新该页面的内容。编辑完成后发 merge request 给我们即可。

{{% notice info %}}
您的改动将会在相关 merge request 被成功合并时自动部署
{{% /notice %}}

## 在线文档

此在线文档也是使用 Hugo 生成的静态网站。只需用一个简单的命令，即：`hugo -t hugo-theme-learn`，[源码在这里（GitHub）](https://github.com/matcornic/hugo-theme-learn)。

{{% notice note %}}
感谢 [Netlify](https://www.netlify.com/) 提供的自动发布与托管服务。相关阅读： [使用 Netlify 自动部署 Hugo 项目](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/)
{{% /notice %}}
