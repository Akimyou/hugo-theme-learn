---
title: 安装
weight: 15
---

只需几步，即可初始化一个新网站。如果一点儿也不了解 Hugo，强烈建议先学习下这个文档 [Hugo 新手必读] (https://gohugo.io/overview/quickstart/)。

## 创建项目


用 Hugo 的 `new` 命令创建新网站。

```
hugo new site <项目路径>
```

## 安装主题

根据 [此文档](https://gohugo.io/themes/installing/)，安装 **Hugo-theme-learn** 主题。

该主题的 git 仓库地址: https://github.com/matcornic/hugo-theme-learn.git

或者，也可以 [下载该主题的 zip 包](https://github.com/matcornic/hugo-theme-learn/archive/master.zip) 后，解压到项目的主题目录下。

## 基础配置

构建网站时，可通过配置 `--theme` 指定默认主题。强烈建议，编辑配置文件将此主题设为默认。另外可配置搜索功能的范围。

```toml
# 设置默认主题
theme = "hugo-theme-learn"

# 设置搜索范围
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

## 新建章节页面

章节页面可嵌套其他页面，有特殊的样式，通常只包含：_章节编号、章节名称与章节简介_ 。

```
### 章节 1

# 基础

了解此 Hugo 主题的内容以及核心概念。
```

渲染结果（请脑补下中文）

![章节页面](/basics/installation/images/chapter.png?classes=shadow&width=60pc)

**Hugo-theme-learn** 提供相关的 原型（archetypes），可方便创建网站的页面结构。可通过以下命令创建你的第一个章节页面。

```
hugo new --kind chapter basics/_index.md
```

打开生成的文件，可看到顶部有属性 `chapter=true`，代表此页面为章节页面。

默认无论是章节页面还是普通页面，创建时均是 草稿（draft）。如需渲染显示，需要将属性 `draft: true` 移除。

## 新建内容页面

接下来，创建内容页面。有两种方式在章节页面下创建内容页面：

```
hugo new basics/first-content.md
hugo new basics/second-content/_index.md
```

请随意编辑这些文件，可添加一些内容以及替换 `title` 的值来更改标题。

## 在本地运行网站

运行此命令

```
hugo serve
```

访问 `http://localhost:1313`

可发现：

1. 网站左侧的菜单有 **基础** 项目，其包含两个子项目，子项目的名称与之前创建的文件的 `title` 属性相同
2. 网站主页有自定义网站相关的教程
3. 运行 `hugo serve` 命令，当文件保存时页面也会立刻刷新，炫酷！

## 构建网站

网站准备发布时，只要运行这个命令：

```
hugo
```

此命令会生成包含网站所有内容的 `public` 文件夹，将其部署到任意 Web 服务器上即可。

{{% notice note %}}
此网站可以通过 [Netlify](https://www.netlify.com/) 进行自动构建与部署 (阅读更多 [自动构建与部署 Hugo 站点](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/))。也可使用 Github pages 服务 [Github pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)。
{{% /notice %}}
