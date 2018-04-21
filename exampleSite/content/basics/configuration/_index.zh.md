---
date: 2016-04-09T16:50:16+02:00
title: 配置
weight: 20
---

## 全局参数

**Hugo-theme-learn** 提供如下的许多配置项，可在 [Hugo 全局配置文件](https://gohugo.io/overview/configuration/) `config.toml` 中使用（此处配置的是默认值）。

注意，部分参数会在文档的其他章节详细解释。

```toml
[params]
  # 编辑此页相关 URL 地址的前缀，显示为每个页面的右上角的 “编辑此页” 按钮
  # 常用于提供其他人也可编辑文档并提交合并请求的能力
  # 可查看本文档项目 config.toml 的配置，参考一下
  editURL = ""
  # 网站的作者，在 meta 标签中使用
  author = ""
  # 网站的描述，在 meta 标签中使用
  description = ""
  # 是否在已访问页面的菜单项目上显示标记
  showVisitedLinks = false
  # 是否禁用搜索功能，搜索栏将隐藏
  disableSearch = false
  # 是否禁用网站更新时 Javascript 与 CSS 缓存的自动失效
  # 可设置为 ture 禁用此行为（某些代理服务器无法很好地处理此优化）
  disableAssetsBusting = false
  # 是否关闭行内代码的复制按钮
  disableInlineCopyToClipBoard = false
  # 是否关闭默认生成快捷导航菜单项目的标题
  disableShortcutsTitle = false
  # 是否禁用多语言站点的多语言切换按钮
  disableLanguageSwitchingButton = false
  # 菜单项目的排序依据，"权重" (weight) 或 "标题" (title)，默认是 "权重"
  ordersectionsby = "weight"
  # 改变默认主题颜色风格：红色风格 (red)，红色风格 (blue)，绿色风格 (green)
  themeVariant = ""
```

## 激活搜索

在 `config.toml` 中添加以下内容（可能已默认添加）

```toml
[outputs]
home = [ "HTML", "RSS", "JSON"]
```
Learn theme 使用最新版 Hugo（版本 20+）提供的新特性生成 index.json 文件。lunr.js 可使用该文件，提供搜索功能。

> Hugo 在 public 文件夹根路径下生成 lunrjs 用的 index.json 文件。
> 当使用 `hugo server` 运行网站时，Hugo 会在内部生成该文件，不会出现在文件系统中。
