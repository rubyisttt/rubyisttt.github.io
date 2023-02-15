---
title: "导航"
permalink: /docs/navigation/
excerpt: "如何定制主导航和启用面包屑链接的说明。"
last_modified_at: 2018-03-20T15:59:40-04:00
toc: true
---

通过 Jekyll 的数据文件定制站点的导航链接。

## 主菜单

主菜单链接使用了“更多”设计模式。也就是说，根据水平宽度的不同，更多的菜单链接项会保存在一个可以展开的菜单中。

定义这些链接，通过在 `_data/navigation.yml` 的 `main` 键下添加成对的 `title` 和 `url` 值即可：

```yaml
main:
  - title: "Quick-Start Guide"
    url: /docs/quick-start-guide/
  - title: "Posts"
    url: /year-archive/
  - title: "Categories"
    url: /categories/
  - title: "Tags"
    url: /tags/
  - title: "Pages"
    url: /page-archive/
  - title: "Collections"
    url: /collection-archive/
  - title: "External Link"
    url: https://google.com
```

这将给您一个自适应的主菜单，例如：

![priority plus masthead animation]({{ "/assets/images/mm-priority-plus-masthead.gif" | relative_url }})

您还可以在 `main` 下选择为每个 `title` 添加一个 `description` 值——用于在用户鼠标光标悬停在桌面浏览器的链接上时显示一个提示信息。

**专业提示：** 将最重要链接放在最前面，以便其一直显示，而不是藏在**菜单开关**里。
{: .notice--info}

## 面包屑（测试）

启用面包屑链接可以更好的帮助访问者深层使用网站。由于实现该功能的方法并不是十分靠谱，所以生成的链接有时并不是很准确。所以，最好的做法是：

1. 使用基于 Permalink 结构的分类，例如 `permalink: /:categories/:title/`
2. 手动为每个分类创建 Page，或者使用诸如 [jekyll-archives](https://github.com/jekyll/jekyll-archives) 的插件自动生成。如果这些 Page 的面包屑链接不存在，系统将崩溃。

![breadcrumb navigation example]({{ "/assets/images/mm-breadcrumbs-example.jpg" | relative_url }})

```yaml
breadcrumbs: true  # disabled by default
```

面包屑功能起始链接文本和分隔符可以在 `_data/ui-text.yml` 中修改。

```yaml
breadcrumb_home_label : "Home"
breadcrumb_separator  : "/"
```

像 `Start > Blog > My Awesome Post` 这样的面包屑链接您可以这样设置：

```yaml
breadcrumb_home_label : "Start"
breadcrumb_separator  : ">"
```

## 定制边栏导航菜单

查阅[**边栏**文档]({{ "/docs/layouts/#custom-sidebar-navigation-menu" | relative_url }})获取设置定制的导航菜单相关信息。
