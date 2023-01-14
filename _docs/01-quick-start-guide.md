---
title: "快速上手指南"
permalink: /docs/quick-start-guide/
excerpt: "How to quickly install and setup Minimal Mistakes for use with GitHub Pages."
last_modified_at: 2021-06-07T08:48:05-04:00
redirect_from:
  - /theme-setup/
toc: true
---

Minimal Mistakes 已开发更易使用的[基于 Gem 的主题](http://jekyllrb.com/docs/themes/)，而且在 GitHub Pages 发布时可以使用 100% 兼容的远程主题。

**如果您欣赏这个主题，请考虑[赞助我](https://github.com/sponsors/mmistakes)以鼓励和支持我持续开发和维护。**

[!["给我买一杯咖啡"](https://user-images.githubusercontent.com/1376749/120938564-50c59780-c6e1-11eb-814f-22a0399623c5.png)](https://www.buymeacoffee.com/mmistakes)

[![通过 PayPal 支持](https://cdn.jsdelivr.net/gh/twolfson/paypal-github-button@1.0.0/dist/button.svg)](https://www.paypal.me/mmistakes)
{: style="margin-top: 0.5em;"}

## 安装主题

如果您运行的是 Jekyll v3.7+ 并且可以自行托管，您可以选择使用基于 Gem 形式的主题。

[^structure]: 查阅[**框架结构**页]({{ "/docs/structure/" | relative_url }})以浏览主题文件列表和它们的作用。

**专业提示：** 如果您复刻（Fork）了 Minimal Mistakes 主题，请确保删除 `/docs` 和 `/test` 文件夹。这些文件夹内是主题的文档和测试页，您可能不需要这些打乱您的代码库的信息。
{: .notice--info}

**备注：** 主题使用 [jekyll-include-cache](https://github.com/benbalter/jekyll-include-cache) 插件（需要在 `Gemfile` 中添加安装，然后在 `_config.yml` 的  `plugins` 数列中添加）。不安装则在构建时抛出 `Unknown tag 'include_cached'` 错误。
{: .notice--warning}

### 基于 Gem 的方法

使用基于 Gem 的主题，诸如 `assets`、`_layouts`、`_includes` 和 `_sass` 这些目录都存储在主题 Gem 之中，您是看不见的。这是最简单的安装和更新方式，因为这种方式下您不需要管理任何主题文件。

安装基于 Gem 的主题：

1. 添加下面代码到 `Gemfile`：

   ```ruby
   gem "minimal-mistakes-jekyll"
   ```

2. 通过运行下面的 [Bundler](https://bundler.io/) 命令获取和更新 Gem：

   ```bash
   bundle
   ```

3. 在您的项目 Jekyll `_config.yml` 文件中设置  `theme`：

   ```yaml
   theme: minimal-mistakes-jekyll
   ```

更新主题运行 `bundle update`。

### 远程主题方法

远程主题同 Gem 主题类似，但是不需要修改 `Gemfile` 或者白名单，将其首选托管于 GitHub Pages。

安装远程主题：

1. 用下面内容创建（取代）您的 `Gemfile` 内容：

   ```ruby
   source "https://rubygems.org"
   gem "github-pages", group: :jekyll_plugins
   gem "jekyll-include-cache", group: :jekyll_plugins
   ```

2. 添加 `jekyll-include-cache` 到 `_config.yml` 的 `plugins` 组。

3. 通过运行下列 [Bundler](https://bundler.io/) 命令获取或者更新绑定的 Gem：

   ```bash
   bundle
   ```

4. 添加 `remote_theme: "mmistakes/minimal-mistakes@4.24.0"` 到您的 `_config.yml` 文件。移除任何其它的 `theme:` 或者 `remote_theme:` 条目。

您也可以选择设定一个分支、[Tag](https://github.com/mmistakes/minimal-mistakes/tags) 或者提交使用添加一个 @ 和 Git 引用（例如 `mmistakes/minimal-mistakes@4.9.0` 或者 `mmistakes/minimal-mistakes@bbf3cbc5fd64a3e1885f3f99eb90ba92af84063d`）。当返回旧版主题时这很有用。如果您不指定一个 Git 引用，则会使用 `master` 分支的最新版。

**在找一个示例吗？** 获得一个托管于 Github Pages 的马上可以运行的站点的最快捷方式就是使用 [Minimal Mistakes 远程主题启动器](https://github.com/mmistakes/mm-github-pages-starter/generate)。基于启动器生成一个新的代码库，用您自己的内容取代示例代码，根据您的需要进行定制。
{: .notice--info}

--- 

**备注：** 您的 Jekyll 站点应该在 <http://USERNAME.github.io> 立马可视。如果没有出现，您可以通过**定制您的站点**强制重新编译（更多细节见后面章节）
{: .notice--warning}

如果您在同一个 GitHub 用户名下托管了几个基于 Jekyll 的站点，您需要使用项目页代替用户页。您必须重命名代码库为不同于 **USERNAME.github.io** 的名字，然后从 `master` 分支创建一个 `gh-pages` 分支。更多细节参阅 [GitHub 文档](https://help.github.com/articles/user-organization-and-project-pages/)。

<figure>
  <img src="{{ '/assets/images/mm-gh-pages.gif' | relative_url }}" alt="creating a new branch on GitHub">
</figure>

您也可以通过复制所有的主题文件[^structure]到您的项目来安装主题。

要这么做需要复刻 [Minimal Mistakes 主题](https://github.com/mmistakes/minimal-mistakes/fork)，然后重命名代码库为 **USERNAME.github.io** --- 替换 **USERNAME** 为您的 GitHub 用户名。

<figure>
  <img src="{{ '/assets/images/mm-theme-fork-repo.png' | relative_url }}" alt="fork Minimal Mistakes">
</figure>

**GitHub Pages 替代品:** 注意您的站点托管商是否可以自由使用和无痛安装（更新）主题？[Netlify][netlify-jekyll], [GitLab Pages][gitlab-jekyll] 和 [持续集成（Continuous Integration ——  CI）服务][ci-jekyll] 您是否已经了解？多数情况下您所需要做的就是连接您的代码库和托管服务商，创建一个简单的配置文件，使用上面讲述的[基于 Ruby Gem 的方法](#ruby-gem-method)安装主题 。
{: .notice--info}

[netlify-jekyll]: https://www.netlify.com/blog/2015/10/28/a-step-by-step-guide-jekyll-3.0-on-netlify/
[gitlab-jekyll]: https://about.gitlab.com/2016/04/07/gitlab-pages-setup/
[ci-jekyll]: https://jekyllrb.com/docs/deployment/automated/#continuous-integration-service

### 删除不需要的东西

如果您复刻或者下载了 `minimal-mistakes-jekyll` 代码库，那么您可以放心删除下列文件夹和文件：

- `.editorconfig`
- `.gitattributes`
- `.github`
- `/docs`
- `/test`
- `CHANGELOG.md`
- `minimal-mistakes-jekyll.gemspec`
- `README.md`
- `screenshot-layouts.png`
- `screenshot.png`

**备注：** 如果复刻了主题，请确保更新了 `Gemfile` 文件。一种情况发现在项目的根目录下构建主题 Gem 时丢失依赖项。正确安装主题的 [`Gemfile`](https://github.com/mmistakes/minimal-mistakes/blob/master/docs/Gemfile)，参阅“[安装依赖项](https://mmistakes.github.io/minimal-mistakes/docs/installation/#install-dependencies)”部分。
{: .notice--warning}

## 创建您的站点

安装 Minimal Mistakes 根据您选择的路径不同，设置也略有不同。

**专业提示：**本站的源代码和内容文件如果您想要复制或者学习，可以在 [`/docs` 文件夹](https://github.com/mmistakes/minimal-mistakes/tree/master/docs)找到。
{: .notice--info}

### 全新开始

从一个空文件夹和 `Gemfile` 开始，您需要复制或者创建[默认的 `_config.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml) 文件。对于每个设置的详细解释参阅[**配置**]({{ "/docs/configuration/" | relative_url }})部分。

从 `v4.5.0` 开始，Minimal Mistakes 的基于 Gem 的主题绑定了必要的数据文件和本地化数据。
如果您已经安装了 [`jekyll-data`](https://github.com/ashmaroli/jekyll-data) 插件，这些数据会被系统自动获取。
如果您在 GitHub Pages 托管网站，您可以复制 [`_data/ui-text.yml`][ui-text.yml] 文件到您的代码库以使本地化功能工作正常。

您需要创建和编辑这些数据文件来定制主题：

- [`_data/ui-text.yml`][ui-text.yml] —— UI 文本[文档]({{ "/docs/ui-text/" | relative_url }})
- [`_data/navigation.yml`][navigation.yml] —— 导航[文档]({{ "/docs/navigation/" | relative_url }})

  [ui-text.yml]: https://github.com/mmistakes/minimal-mistakes/blob/master/_data/ui-text.yml
  [navigation.yml]: https://github.com/mmistakes/minimal-mistakes/blob/master/_data/navigation.yml

### 从 `jekyll new` 开始

使用 `jekyll new` 命令创建站点基本框架需要修改一些创建站点时生成的文件。

编辑 `_config.yml`。然后：

- 用修改的 [Minimal Mistakes `index.html`](https://github.com/mmistakes/minimal-mistakes/blob/master/index.html) 取代 `<site root>/index.md`。如果使用 [`home` 版式]({{ "/docs/layouts/#home-page" | relative_url }})需要在 **_config.yml** 中添加必要的代码行以确保启用分页功能；
- 修改 `_posts/0000-00-00-welcome-to-jekyll.markdown` 中的 `layout: post` 为 `layout: single`；
- 删除 `about.md`，或者至少修改 `layout: page` 为 `layout: single`，并删除到 `icon-github.html` 的引用（或者如果使用它就[复制到您的 `_includes`](https://github.com/jekyll/minima/tree/master/_includes)）。

### 迁移到 Gem 版本

如果您迁移一个已经使用了 Minimal Mistakes 主题并且没有做任何定制的站点相对比较容易。

删除下列文件夹和文件：

```terminal
├── _includes
├── _layouts
├── _sass
├── assets
|  ├── css
|  ├── fonts
|  └── js
```

因为这些文件已经绑定在主题的 Gem 中了，所以您不再需要它们了——除非您想要进行[定制化修改](https://jekyllrb.com/docs/themes/#overriding-theme-defaults)。

**备注：** 清理 `assets` 文件夹时要确保删除您添加所有文件。这包括图像、CSS、JavaScript 等，这些文件[在主题 Gem 中已经绑定](https://github.com/mmistakes/minimal-mistakes/tree/master/assets).。
{: .notice--warning}

从 `v4.5.0` 开始，默认语言文件会通过 [`jekyll-data`](https://github.com/ashmaroli/jekyll-data) 插件（如果已经安装）自动读取。对于托管于 GitHub Pages 的站点，由于 `jekyll-data` 插件 [GitHub Pages 不支持](https://docs.github.com/en/github/working-with-github-pages/about-github-pages-and-jekyll#plugins)所以您需要复制 [`_data/ui-text.yml`][ui-text.yml] 文件。

如果您已经定制修改了某些文件，那么就将其留下，将未修改文件删除。如果操作正确您修改的文件将[覆盖](https://jekyllrb.com/docs/themes/#overriding-theme-defaults)主题绑定的文件而被 Jekyll 使用。

#### 升级 Gemfile

用 `gem "jekyll", "~> 3.5"` 替换 `gem "github-pages` 或者 `gem "jekyll"`。您需要最新版本的 Jekyll[^update-jekyll]，才能使 Minimal Mistakes 正常运行和正确加载所有主题资源文件，下面这行命令强制 Bundler 更新 Jekyll。

[^update-jekyll]: 您也可以运行 `bundle update jekyll` 来升级 Jekyll。

添加 Minimal Mistakes 主题 Gem： 

```ruby
gem "minimal-mistakes-jekyll"
```

运行完成时您的 `Gemfile` 看起来应该这样：

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 3.7"
gem "minimal-mistakes-jekyll"
```

然后运行 `bundle update`，添加 `theme: minimal-mistakes-jekyll` 到 `_config.yml`。

**v4 惊天大修改：** Image headers、Overlays、Teasers、[Galleries]({{ "/docs/helpers/#gallery" | relative_url }}) 和 [feature rows]({{ "/docs/helpers/#feature-row" | relative_url }}) 路径都已经修改，现在需要一个全的路径。过去是 `image: filename.jpg`，现在需要使用全的路径，例如：`image: /assets/images/filename.jpg`。预置路径现在是 `/assets/images/`，但是可以修改，甚至可以使用外部托管图像。这个图像引用在 `_config.yml` 和 `author.yml` 使用都是一样的。
{: .notice--danger}

---

就这些！如果一切顺利，运行 `bundle exec jekyll serve` 应该就看到您的站点了。
