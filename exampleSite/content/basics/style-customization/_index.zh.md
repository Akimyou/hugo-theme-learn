---
date: 2016-04-09T16:50:16+02:00
title: 自定义样式
weight: 25
---

**Hugo-theme-learn** 通过定义多种 [局部模版（partials）](https://gohugo.io/templates/partials/)，使得整体拥有较高的可配置性。

在 `themes/hugo-theme-learn/layouts/partials/` 目录，可找到所有的局部模版。如需修改内容，请不要直接修改主题的代码。参考 [这篇文章](https://gohugo.io/themes/customizing/)，在自己网站项目的 `layouts/partials` 目录下创建新的局部模版。局部模版有优先级关系，如下：

主题定义的局部模版：

- *header*: 页面的头部（包含面包屑导航）。_请勿覆盖_
- *custom-header*: 页面头部的自定义部分，当需要自定义样式时可覆盖，注意别忘记包含 `style` 标签
- *footer*: 页面的尾部。_请勿覆盖_
- *custom-footer*:  页面尾部的自定义部分，当需要自定义脚本时可覆盖，注意别忘记包含 `srcipt` 标签
- *favicon*: 网站的 favicon
- *logo*: 网站的 logo，位于左上角
- *meta*: HTML 的 meta 标签, 可覆盖修改默认 meta 规则
- *menu*: 左侧的菜单。 _请勿覆盖_
- *menu-footer*: 左侧菜单的尾部
- *search*: 搜索框
- *toc*: 页面内容中的表格

## 修改网站 Logo

在 `layouts/partials/` 文件夹下创建 `logo.html` 文件，可往里面写入任何内容。还可以使用 `img` 标签引用 *static* 目录下的图片做 logo，或者直接使用 SVG ！

{{% notice note %}}
logo 图片的大小会自动调整
{{% /notice %}}

## 修改网站 favicon

如果 favicon 是 png 文件，只需将其放到项目的 `static/images/` 文件夹下命名为 `favicon.png` 即可。

如果想要改变生成 favicon 的默认行为，可在 `layouts/partials/` 文件夹下创建 `favicon.html` 文件，往里写入类似这样内容：

```html
<link rel="shortcut icon" href="/images/favicon.png" type="image/x-icon" />
```

## 设置默认配色风格 {#theme-variant}

**Hugo Learn theme** 提供 3 种预设配色风格，但也完全可以创建自定义风格！预设风格的配色方案基于 [Grav Learn Theme](https://learn.getgrav.org/)。

### 红色风格

```toml
[params]
  # 设置默认配色风格，可选项："red", "blue", "green"
  themeVariant = "red"
```

![红色风格](/basics/style-customization/images/red-variant.png?width=60pc)

### 蓝色风格

```toml
[params]
  # 设置默认配色风格，可选项："red", "blue", "green"
  themeVariant = "blue"
```

![蓝色风格](/basics/style-customization/images/blue-variant.png?width=60pc)

### 绿色风格

```toml
[params]
  # 设置默认配色风格，可选项："red", "blue", "green"
  themeVariant = "green"
```

![绿色风格](/basics/style-customization/images/green-variant.png?width=60pc)

### 自定义风格

首先，在项目的 `static/css` 文件夹下新建一个以 `theme` 打头的 CSS 文件（例如 _mine_ 主题 `static/css/theme-mine.css`）。复制以下内容到文件中并修改颜色相关的 CSS 变量。

```css

:root{

    --MAIN-TEXT-color:#323232; /* 默认内容文本颜色 */
    --MAIN-TITLES-TEXT-color: #5e5e5e; /* 默认标题颜色 h2-h3-h4-h5 */
    --MAIN-LINK-color:#1C90F3; /* 链接颜色 */
    --MAIN-LINK-HOVER-color:#167ad0; /* 选中的链接颜色 */
    --MAIN-ANCHOR-color: #1C90F3; /* 标题锚点颜色 */

    --MENU-HEADER-BG-color:#1C90F3; /* 菜单头部背景颜色 */
    --MENU-HEADER-BORDER-color:#33a1ff; /* 菜单头部边框颜色 */

    --MENU-SEARCH-BG-color:#167ad0; /* 菜单搜索框背景颜色 (也是边框与图标的颜色) */
    --MENU-SEARCH-BOX-color: #33a1ff; /* 覆盖菜单搜索框边框颜色 */
    --MENU-SEARCH-BOX-ICONS-color: #a1d2fd; /* 覆盖菜单搜索框图标颜色 */

    --MENU-SECTIONS-ACTIVE-BG-color:#20272b; /* 选中菜单项目与其子项目背景颜色 */
    --MENU-SECTIONS-BG-color:#252c31; /* 未选中菜单项目背景颜色 */
    --MENU-SECTIONS-LINK-color: #ccc; /* 菜单项目链接颜色 */
    --MENU-SECTIONS-LINK-HOVER-color: #e6e6e6;  /* 菜单项目链接选中颜色 */
    --MENU-SECTION-ACTIVE-CATEGORY-color: #777; /* 选中菜单项目文本颜色 */
    --MENU-SECTION-ACTIVE-CATEGORY-BG-color: #fff; /* 选中菜单项目背景颜色 */

    --MENU-VISITED-color: #33a1ff; /* 菜单已访问标记颜色 */
    --MENU-SECTION-HR-color: #20272b; /* 菜单项目分割线颜色 */

}

body {
    color: var(--MAIN-TEXT-color) !important;
}

textarea:focus, input[type="email"]:focus, input[type="number"]:focus, input[type="password"]:focus, input[type="search"]:focus, input[type="tel"]:focus, input[type="text"]:focus, input[type="url"]:focus, input[type="color"]:focus, input[type="date"]:focus, input[type="datetime"]:focus, input[type="datetime-local"]:focus, input[type="month"]:focus, input[type="time"]:focus, input[type="week"]:focus, select[multiple=multiple]:focus {
    border-color: none;
    box-shadow: none;
}

h2, h3, h4, h5 {
    color: var(--MAIN-TITLES-TEXT-color) !important;
}

a {
    color: var(--MAIN-LINK-color);
}

.anchor {
    color: var(--MAIN-ANCHOR-color);
}

a:hover {
    color: var(--MAIN-LINK-HOVER-color);
}

#sidebar ul li.visited > a .read-icon {
	color: var(--MENU-VISITED-color);
}

#body a.highlight:after {
    display: block;
    content: "";
    height: 1px;
    width: 0%;
    -webkit-transition: width 0.5s ease;
    -moz-transition: width 0.5s ease;
    -ms-transition: width 0.5s ease;
    transition: width 0.5s ease;
    background-color: var(--MAIN-LINK-HOVER-color);
}
#sidebar {
	background-color: var(--MENU-SECTIONS-BG-color);
}
#sidebar #header-wrapper {
    background: var(--MENU-HEADER-BG-color);
    color: var(--MENU-SEARCH-BOX-color);
    border-color: var(--MENU-HEADER-BORDER-color);
}
#sidebar .searchbox {
	border-color: var(--MENU-SEARCH-BOX-color);
    background: var(--MENU-SEARCH-BG-color);
}
#sidebar ul.topics > li.parent, #sidebar ul.topics > li.active {
    background: var(--MENU-SECTIONS-ACTIVE-BG-color);
}
#sidebar .searchbox * {
    color: var(--MENU-SEARCH-BOX-ICONS-color);
}

#sidebar a {
    color: var(--MENU-SECTIONS-LINK-color);
}

#sidebar a:hover {
    color: var(--MENU-SECTIONS-LINK-HOVER-color);
}

#sidebar ul li.active > a {
    background: var(--MENU-SECTION-ACTIVE-CATEGORY-BG-color);
    color: var(--MENU-SECTION-ACTIVE-CATEGORY-color) !important;
}

#sidebar hr {
    border-color: var(--MENU-SECTION-HR-color);
}
```

然后，将 `themeVariant` 设置为自定义主题风格的名称即可。

```toml
[params]
  # 设置默认配色风格，可选项："red", "blue", "green"
  themeVariant = "mine"
```
