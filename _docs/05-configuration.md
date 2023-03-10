---
title: "配置"
permalink: /docs/configuration/
excerpt: "设置配置选项和定制主题。"
last_modified_at: 2021-05-11T10:40:42-04:00
toc: true
---

能够影响整个站点的设置是 [Jekyll 的配置文件](https://jekyllrb.com/docs/configuration/)： `_config.yml`，其位置在您的项目的根目录里。如果您的项目还没有这个文件，您就需要基于主题的[默认 `_config.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml) 复制或者创建它。

**备注：** 基于技术原因，当使用 `jekyll serve` 时，`_config.yml` **不会**自动重新加载。如果您对该文件进行了任何修改，都需要重新启动服务器才能生效。
{: .notice--warning}

花点儿时间看一看主题内的配置文件，大多数配置选项都以注释的方式提供了示例和默认值，详细说明见下面文章。

## 站点设置

### 主题

如果您使用的是基于 Ruby Gem 版本的主题，您需要使用下面的代码激活：

```yaml
theme: minimal-mistakes-jekyll
```

### 款式

使用预置的“skins”可以很容易修改主题的颜色方案：

```yaml
minimal_mistakes_skin: "default" # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
```

**备注：** 如果您修改了主题的 CSS 文件，请确保更新 [`/assets/css/main.scss`](https://github.com/mmistakes/minimal-mistakes/blob/master/assets/css/main.scss) —— 在导入 `minimal-mistakes` 之前包含 `@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin`。
{: .notice--warning}

#### Air 款式： `air`

{:.no_toc}

<figure class="half">
    <a href="{{ site.baseurl }}/assets/images/air-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/air-skin-archive.png"></a>
    <a href="{{ site.baseurl }}/assets/images/air-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/air-skin-post.png"></a>
    <figcaption>静谧，蓝色。</figcaption>
</figure>

#### Aqua 款式： `aqua`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/aqua-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/aqua-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/aqua-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/aqua-skin-post.png"></a>
  <figcaption>平静如水。</figcaption>
</figure>

#### Contrast 款式： `contrast`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/contrast-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/contrast-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/contrast-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/contrast-skin-post.png"></a>
  <figcaption>拥有粗体蓝色链接和反转色系地脚的复古感。</figcaption>
</figure>

#### Dark 款式： `dark`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/dark-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/dark-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/dark-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/dark-skin-post.png"></a>
  <figcaption>反转色系，黑底白字。</figcaption>
</figure>

#### Dirt 款式： `dirt`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/dirt-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/dirt-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/dirt-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/dirt-skin-post.png"></a>
  <figcaption>乡土气息。</figcaption>
</figure>

#### Mint 款式： `mint`

{:.no_toc}

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/mint-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/mint-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/mint-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/mint-skin-post.png"></a>
  <figcaption>薄荷新绿。</figcaption>
</figure>

#### Neon 款式： `neon`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/neon-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/neon-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/neon-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/neon-skin-post.png"></a>
  <figcaption>反转色系，暗底白字。</figcaption>
</figure>

#### Neon 款式： `plum`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/plum-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/plum-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/plum-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/plum-skin-post.png"></a>
  <figcaption>高贵典雅的紫色。</figcaption>
</figure>

#### Sunrise 款式： `sunrise`

<figure class="half">
  <a href="{{ site.baseurl }}/assets/images/sunrise-skin-archive-large.png"><img src="{{ site.baseurl }}/assets/images/sunrise-skin-archive.png"></a>
  <a href="{{ site.baseurl }}/assets/images/sunrise-skin-post-large.png"><img src="{{ site.baseurl }}/assets/images/sunrise-skin-post.png"></a>
  <figcaption>桔色和红色。</figcaption>
</figure>

### 站点本地设置

`site.locale` 用于声明站点内每个页面使用的基本语言。

_示例：_ `locale: "en-US"` 为站点设置 `lang` 属性为 _美国_ 英语，而 `en-GB` 则表示使用的是`英国`英语。国家代码可选，省略如 `locale: "en"` 也是可以的。查找您的语言和国家代码请[参考表格](<https://msdn.microsoft.com/en-us/library/ee825488(v=cs.20).aspx>)。

正确设置 locale 很重要——因为它还关联 [**UI Text**]({{ "/docs/ui-text/" | relative_url }}) 数据文件中的本地化文本。不当的匹配可能会导致部分 UI 文本缺失（例如，按钮标签、栏目标题等）。

**备注：**主题自带英文（`en`、`en-US`、`en-GB`）本地化文本。如果您想修改 `_config.yml` 中 `locale`，大部分 UI 文本都会变成空白。要想避免这种情况，需要在 `_data/ui-text.yml` 中添加适当的键和对应的翻译文本。
{: .notice--warning}

### 站点标题

站点名字。通常出现在主题的站点名字的位置和 `<title>` 标签。

_示例：_ `title: "My Awesome Site"`

您也可以定制对 SEO 友好的页面标题分隔符。

_示例：_ `title_separator: "|"` 会生成诸如 `Sample Page | My Awesome Site` 的页面标题。

**备注：** 长的站点标题会破坏标题布局。所以尽量避免使用长的口号做为标题，例如 `My Awesome Site is the Best Because I Say So`。
{: .notice--warning}

### 站点子标题

在站点标题下面使用的短的口号。

_示例：_ `subtitle: "Version 2.0"`

### 站点名字

通常会设定一个站点的作者。不要着急，您可以在 post、page 和 collection 文档中通过设定来覆盖默认值。
_示例：_ `name: "Michael Rose"`.

**专家提醒：** If you want to get crafty with your YAML you can use [anchors](http://www.yaml.org/spec/1.2/spec.html#id2785586) to reuse values. For example `foo: &var "My String"` allows you to reuse `"My String"` elsewhere in `_config.yml` like so... `bar: *var`. You'll see a few examples of this in the provided Jekyll config.
{: .notice--info}

### 站点简介

Fairly obvious. `site.description` describes the site. Used predominantly in meta descriptions for improving SEO.

_示例：_ `description: "A flexible Jekyll theme for your blog or site with a minimalist aesthetic."`

### 站点 URL

The base hostname and protocol for your site. If you're hosting with GitHub Pages this will be something like `url: "https://mmistakes.github.io"` or `url: "https://mademistakes.com"` if you have a custom domain name.

GitHub Pages now [forces `https://` for new sites](https://help.github.com/articles/securing-your-github-pages-site-with-https/) so be mindful of that when setting your URL to avoid mixed-content warnings.

**备注：** Jekyll 3.3 overrides this value with `url: http://localhost:4000` when running `jekyll serve` locally in development. If you want to avoid this behavior set `JEKYLL_ENV=production` to [force the environment](https://jekyllrb.com/docs/configuration/environments/) to production.
{: .notice--warning}

### 站点基础 URL

This little option causes all kinds of confusion in the Jekyll community. If you're not hosting your site as a GitHub Pages Project or in a subfolder (eg: `/blog`), then don't mess with it.

In the case of the Minimal Mistakes demo site it's hosted on GitHub at <https://mmistakes.github.io/minimal-mistakes>. To correctly set this base path I'd use `url: "https://mmistakes.github.io"` and `baseurl: "/minimal-mistakes"`.

For more information on how to properly use `site.url` and `site.baseurl` as intended by the Jekyll maintainers, check [Parker Moore's post on the subject](https://byparker.com/blog/2014/clearing-up-confusion-around-baseurl/).

**备注：** When using `baseurl` remember to include it as part of your path when testing your site locally. Values of `url:` and `baseurl: "/blog"` would make your local site visible at `http://localhost:4000/blog` and not `http://localhost:4000`.
{: .notice--warning}

### 站点代码库

Add your repository name with organization to your site's configuration file, `_config.yml`.

```yaml
repository: "username/repo-name"
```

"NWO" stands for "name with owner." It is GitHub lingo for the username of the owner of the repository plus a forward slash plus the name of the repository, e.g. `mmistakes/minimal-mistakes`, where **mmistakes** is the owner and **minimal-mistakes** is the repository name.

Your `site.github.*` fields should fill in like normal. If you run Jekyll with the --verbose flag, you should be able to see all the API calls made.

If you don't set `repository` correctly you may see the following error when trying to `serve` or `build` your Jekyll site:

**Liquid Exceptions:** No repo name found. Specify using `PAGES_REPO_NWO` environment variables, `repository` in your configuration, or set up `origin` git remote pointing to your github.com repository.
{: .notice--danger}

For more information on how `site.github` data can be used with Jekyll check out [`github-metadata`'s documentation](https://github.com/jekyll/github-metadata).

### 站点脚本

Add scripts to the `<head>` or closing `</body>` elements by assigning paths to either `head_scripts` and/or `footer_scripts`.

For example, to add a CDN version of jQuery to page's head along with a custom script you'd do the following:

```yaml
head_scripts:
  - https://code.jquery.com/jquery-3.2.1.min.js
  - /assets/js/your-custom-head-script.js
```

Consult the [JavaScript documentation]({{ site.baseurl }}{% link _docs/17-javascript.md %}) for more information on working with theme scripts.
{: .notice--info}

### 站点默认 Teaser 图像

To assign a fallback teaser image used in the "**Related Posts**" module, place a graphic in the `/assets/images/` directory and add the filename to `_config.yml` like so:

```yaml
teaser: /assets/images/500x300.png
```

This image can be overridden at anytime by applying the following to a document's YAML Front Matter.

```yaml
header:
  teaser: /assets/images/my-awesome-post-teaser.jpg
```

<figure>
  <img src="{{ '/assets/images/mm-teaser-images-example.jpg' | relative_url }}" alt="teaser image example">
  <figcaption>Example of teaser images found in the related posts module.</figcaption>
</figure>

### 站点 Masthead 标志

To insert a logo before the site title, place a graphic in the `/assets/images/` directory and add the filename to `_config.yml`:

```yaml
logo: "/assets/images/88x88.png"
```

<figure>
  <img src="{{ '/assets/images/mm-masthead-logo.png' | relative_url }}" alt="masthead with logo and custom title">
  <figcaption>Example of masthead with logo and custom title.</figcaption>
</figure>

### 站点 Masthead 标题

By default your site title is used in the masthead. You can override this text by adding the following to your `_config.yml`:

```yaml
masthead_title: "My Custom Title"
```

### 面包屑导航（测试中）

Enable breadcrumb links to help visitors better navigate deep sites. Because of the fragile method of implementing them they don't always produce accurate links reliably. For best results:

1. Use a category based permalink structure e.g. `permalink: /:categories/:title/`
2. Manually create pages for each category or use a plugin like [jekyll-archives][jekyll-archives] to auto-generate them. If these pages don't exist breadcrumb links to them will be broken.

![breadcrumb navigation example]({{ "/assets/images/mm-breadcrumbs-example.jpg" | relative_url }})

```yaml
breadcrumbs: true  # disabled by default
```

Breadcrumb start link text and separator character can both be changed in the [UI Text data file]({{ "/docs/ui-text/" | relative_url }}).

### Post 日期

Enable post date snippets with `show_date: true` in YAML Front Matter.

![post date example]({{ "/assets/images/mm-post-date-example.png" | relative_url }})

Instead of adding `show_date: true` to each post, apply as a default in `_config.yml` like so:

```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      show_date: true
```

To disable post date for a post, add `show_date: false` to its YAML Front Matter, overriding what was set in `_config.yml`.

When dates are shown on blog posts or pages, a date format will be chosen to format the date string. The default format is `"%B %-d, %Y"`, which will be displayed like "February 24, 2016". You can choose your date format by referencing this [cheat sheet](https://www.shortcutfoo.com/app/dojos/ruby-date-format-strftime/cheatsheet). For example, use your date format in `_config.yml`.

```yaml
date_format: "%Y-%m-%d"
```

### 阅读时间

Enable estimated reading time snippets with `read_time: true` in YAML Front Matter. `200` has been set as the default words per minute value --- which can be changed by adjusting `words_per_minute:` in `_config.yml`.

![reading time example]({{ "/assets/images/mm-read-time-example.jpg" | relative_url }})

Instead of adding `read_time: true` to each post, apply as a default in `_config.yml` like so:

```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      read_time: true
```

To disable reading time for a post, add `read_time: false` to its YAML Front Matter to override what was set in `_config.yml`.

`words_per_minute` can also be adjusted per-page basis by adding to its YAML Front Matter. This is useful for sites with multi-lingual content where you'd like specify a different value from the site config.

```yaml
words_per_minute: 250
```

### Page 元数据分隔符号

To customise the separator between the page date and reading time (if both are enabled), edit `.page__meta-sep::before` in a [custom stylesheet]({{ "/docs/stylesheets/" | relative_url }}).

For example,

```css
.page__meta-sep::before {
  content: "\2022";
  padding-left: 0.5em;
  padding-right: 0.5em;
}
```

### 评论

[**Disqus**](https://disqus.com/), [**Discourse**](https://www.discourse.org/), [**Facebook**](https://developers.facebook.com/docs/plugins/comments), [**utterances**](https://utteranc.es/), [**giscus**](https://giscus.app/) and static-based commenting via [**Staticman**](https://staticman.net/) are built into the theme. First set the comment provider you'd like to use:

| Name             | Comment Provider          |
| ---------------- | ------------------------- |
| **disqus**       | Disqus                    |
| **discourse**    | Discourse                 |
| **facebook**     | Facebook Comments         |
| **staticman_v2** | Staticman v2 / v3         |
| **staticman**    | Staticman v1 (deprecated) |
| **utterances**   | utterances                |
| **giscus**       | giscus                    |
| **custom**       | Other                     |

Then add `comments: true` to each document you want comments visible on.

Instead of adding YAML Front Matter to each document, apply as a default in `_config.yml`. To enable comments for all posts:

```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      comments: true
```

If you add `comments: false` to a post's YAML Front Matter it will override the default and disable comments for just that post.

**备注：** Comments are disabled by default in `development`. To enable when testing/building locally be sure to set
`JEKYLL_ENV=production` to [force the environment](http://jekyllrb.com/docs/configuration/#specifying-a-jekyll-environment-at-build-time) to production.
{: .notice--info}

#### Disqus

To use Disqus you'll need to create an account and [shortname](https://help.disqus.com/customer/portal/articles/466208-what-s-a-shortname-). Once you have both update `_config.yml` to:

```yaml
comments:
  provider: "disqus"
  disqus:
    shortname: "your-disqus-shortname"
```

#### Discourse

For guidance on how to set up Discourse for embedding comments from a topic on a post page, [consult this guide](https://meta.discourse.org/t/embedding-discourse-comments-via-javascript/31963).

```yaml
comments:
  provider: "discourse"
  discourse:
    server: # meta.discourse.org
```

**备注：** Do not include `http://` or `https://` when setting your Discourse `server`. The theme automatically prepends the URL `//`, following a scheme-less pattern.
{: .notice--info}

#### Facebook 评论

To enable Facebook Comments choose how many comments you'd like visible per post and the color scheme of the widget.

```yaml
comments:
  provider: "facebook"
  facebook:
    appid: # optional
    num_posts: # 5 (default)
    colorscheme: # "light" (default), "dark"
```

#### utterances 评论

To use utterances you will need to [install the app](https://github.com/apps/utterances) to your GitHub repository by adding the following to `_config.yml`:

```yaml
repository: # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
```

**备注：** Make sure the repo is public, otherwise your readers will not be able to view the issues/comments. The [issues feature](https://guides.github.com/features/issues/) also needs to be active on your repo.
{: .notice--warning}

To enable utterances on the front end set `comments.provider` and the color theme of the widget.

```yaml
comments:
  provider: "utterances"
  utterances:
    theme: "github-light" # "github-dark"
    issue_term: "pathname"
    label: "comment" # Optional - must be existing label.
```

#### giscus 评论

To use giscus you will need to [install the app](https://github.com/apps/giscus) to your GitHub repository.

The next step is to go to <https://giscus.app> and fill out the desired settings. This will generate JavaScript that will provide you with the settings you will need to configure things below.

You'll need to ensure you've added the following to `_config.yml`:

```yaml
repository: # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
```

**备注：** Make sure the repo is public, otherwise your readers will not be able to view the issues/comments. The [discussions feature](https://docs.github.com/en/discussions) also needs to be active on your repo.
{: .notice--warning}

To enable giscus on the front end set `comments.provider` and the other additional options.

```yaml
comments:
  provider: "giscus"
  giscus:
    repo_id              : # Shown during giscus setup at https://giscus.app
    category_name        : # Full text name of the category
    category_id          : # Shown during giscus setup at https://giscus.app
    discussion_term      : # "pathname" (default), "url", "title", "og:title"
    reactions_enabled    : # '1' for enabled (default), '0' for disabled
    theme                : # "light" (default), "dark", "dark_dimmed", "transparent_dark", "preferred_color_scheme"
```

#### 通过 Staticman 进行的静态评论

Transform user comments into `_data` files that live inside of your GitHub repository by enabling Staticman.

**备注：** Looking to migrate comments from a WordPress based site? Give [this tool](https://github.com/arthurlacoste/wordpress-comments-jekyll-staticman) a try.
{: .notice--info}

**备注：** Please note that as of September 2018, Staticman is reaching GitHub API limits due to its popularity, and it is recommended by its maintainer that users deploy their own instances for production (use `site.staticman.endpoint`).  Consult the Staticman "[Get Started](https://staticman.net/docs/index.html)" guide for more info.
{: .notice--warning}

##### Add Staticman as a collaborator on GitHub (legacy)

1. Allow Staticman push access to your GitHub repository by clicking on **Settings**, then the **Collaborators** tab and adding your GitHub bot as a collaborator.
2. To accept the pending invitation visit: `https://{your Staticman v2/3 API}/v[2|3]/connect/{your GitHub username}/{your repository name}`.

**备注：** The new GitHub App authentication method is recommended for GitHub repositories to avoid the API rate limit.
{: .notice--info}

##### Configure Staticman

###### Staticman v3

Due to the [support for GitLab](https://github.com/eduardoboucas/staticman/pull/219), the URL scheme has been changed.  Between `v3/entry/` and `/{your Git username}`, one needs to input a Git service provider (either `github` or `gitlab`).  For example

    https://{your Staticman v3 API}/v3/entry/github/{your Git username}/{your repository name}/...

```yaml
# _config.yml (defaults)
repository  : # Git username/repo-name e.g. "mmistakes/minimal-mistakes"
comments:
  provider  : "staticman_v2"
  staticman:
    branch    : "master"
    endpoint  : https://{your Staticman v3 API}/v3/entry/github/
```

###### Staticman v2

Default settings have been provided in [`staticman.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/staticman.yml) and are commented to guide you through setup. View the [full list of configurations](https://staticman.net/docs/configuration).

```yaml
# staticman.yml (defaults)
comments:
  allowedFields      : ["name", "email", "url", "message"]
  branch             : "master"
  commitMessage      : "New comment by {fields.name}"
  filename           : "comment-{@timestamp}"
  format             : "yaml"
  generatedFields:
    date:
      type           : "date"
      options:
        format       : "iso8601"
  moderation         : true
  path               : "_data/comments/{options.slug}"
  requiredFields     : ["name", "email", "message"]
  transforms:
    email            : md5
```

These settings need to be added to your `_config.yml` file as well:

```yaml
# _config.yml (defaults)
repository  : # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
comments:
  provider  : "staticman_v2"
  staticman:
    branch    : "master"
```

**Branch setting:** This is the branch comment files will be sent to via pull requests. If you host your site on GitHub Pages it will likely be `master` unless your repo is setup as a project --- use `gh-pages` in that case.
{: .notice--info}

**备注：** Staticman is currently compatible with GitHub and GitLab based repositories. [Support for GitLab Pages](https://github.com/eduardoboucas/staticman/issues/22) is already available at [Staticman v3](https://github.com/eduardoboucas/staticman/pull/219).
{: .notice--warning}

###### Staticman v1 (deprecated)

Default settings have been provided in `_config.yml`. The important ones to set are `provider: "staticman"`, `branch`, and `path`. View the [full list of configurations](https://staticman.net/docs/configuration).

```yaml
# _config.yml (defaults)
comments:
  provider: "staticman"
staticman:
  allowedFields          : ['name', 'email', 'url', 'message']
  branch                 : "master"
  commitMessage          : "New comment by {fields.name}"
  filename               : comment-{@timestamp}
  format                 : "yml"
  moderation             : true
  path                   : "_data/comments/{options.slug}"
  requiredFields         : ['name', 'email', 'message']
  transforms:
    email                : "md5"
  generatedFields:
    date:
      type               : "date"
      options:
        format           : "iso8601" # "iso8601" (default), "timestamp-seconds", "timestamp-milliseconds"
```

##### Comment moderation

By default comment moderation is enabled in `staticman.yml`. As new comments are submitted Staticman will send a pull request. Merging these in will approve the comment, close the issue, and automatically rebuild your site (if hosted on GitHub Pages).

To skip this moderation step simply set `moderation: false`.

**专家提醒：** Create a GitHub webhook that sends a `POST` request to the following payload URL `https://{your Staticman API URL}/v2/webhook` and triggers a "Pull request" event to delete Staticman branches on merge.
{: .notice--info}

![pull-request webhook]({{ "/assets/images/mm-staticman-pr-webhook.jpg" | relative_url }})

##### reCAPTCHA support (v2 only)

To enable Google's reCAPTCHA to aid in spam detection you'll need to:

1. Apply for [reCAPTCHA API](https://www.google.com/recaptcha) keys and register your site using the reCAPTCHA V2 type.
2. Add your site and secret keys to `staticman.yml` and `_config.yml`. Be sure to properly encrypt your secret key using [Staticman's encrypt endpoint](https://staticman.net/docs/encryption).

```yaml
reCaptcha:
  enabled: true
  siteKey: # "6LdRBykTAAAAAFB46MnIu6ixuxwu9W1ihFF8G60Q"
  secret: # "PznnZGu3P6eTHRPLORniSq+J61YEf+A9zmColXDM5icqF49gbunH51B8+h+i2IvewpuxtA9TFoK68TuhUp/X3YKmmqhXasegHYabY50fqF9nJh9npWNhvITdkQHeaOqnFXUIwxfiEeUt49Yoa2waRR7a5LdRAP3SVM8hz0KIBT4="
```

#### Other comment providers

To use another provider not included with the theme set `provider: "custom"` then add their embed code to `_includes/comments-providers/custom.html`.

### Custom feed URL

By default the theme links to `feed.xml` generated in the root of your site by the **jekyll-feed** plugin. To link to an externally hosted feed update `atom_feed` in `_config.yml` like so:

```yaml
atom_feed:
  path: "http://feeds.feedburner.com/youFeedname"
```

**备注：** By default the site feed is linked in two locations: inside the [`<head>` element](https://github.com/mmistakes/minimal-mistakes/blob/master/_includes/head.html) and at the bottom of every page in the [site footer](https://github.com/mmistakes/minimal-mistakes/blob/master/_includes/footer.html).
{: .notice--info}

### Disable Feed Icons

By default the theme links to `feed.xml` generated in the root of your site by the **jekyll-feed** plugin. To remove the RSS icon in the header and footer, update `atom_feed` in `_config.yml` like so:

```yaml
atom_feed:
  hide: true
```

### Site search

To enable site-wide search add `search: true` to your `_config.yml`.

![masthead search example]({{ "/assets/images/masthead-search.gif" | relative_url }})

#### Lunr (default)

The default search uses [**Lunr**](https://lunrjs.com/) to build a search index of all post and your documents in collections. This method is 100% compatible with sites hosted on GitHub Pages.

To have it index all pages, update `lunr` in `_config.yml` like so:

```yaml
lunr:
  search_within_pages: true
```

**备注：** Only the first 50 words of a post or page's body content is added to the Lunr search index. Setting `search_full_content` to `true` in your `_config.yml` will override this and could impact page load performance.
{: .notice--warning}

#### Algolia

For faster and more relevant search ([see demo](https://mmistakes.github.io/minimal-mistakes-algolia-search/)):

1. Add the [`jekyll-algolia`](https://github.com/algolia/jekyll-algolia) gem to your `Gemfile`, in the `:jekyll_plugins` section.

   ```ruby
   group :jekyll_plugins do
     gem "jekyll-feed"
     gem "jekyll-seo-tag"
     gem "jekyll-sitemap"
     gem "jekyll-paginate"
     gem "jekyll-include-cache"
     gem "jekyll-algolia"
   end
   ```

   Once this is done, download all dependencies by running `bundle install`.

2. Switch search providers from `lunr` to `algolia` in your `_config.yml` file:

   ```yaml
   search_provider: algolia
   ```

3. Add the following Algolia credentials to your `_config.yml` file. *If you don't have an Algolia account, you can open a free [Community plan](https://www.algolia.com/users/sign_up/hacker). Once signed in, you can grab your credentials from [your dashboard](https://www.algolia.com/licensing).*

   ```yaml
   algolia:
     application_id: # YOUR_APPLICATION_ID
     index_name: # YOUR_INDEX_NAME
     search_only_api_key: # YOUR_SEARCH_ONLY_API_KEY
     powered_by: # true (default), false
   ```

4. Once your credentials are setup, you can run the indexing with the following command:

   ```
   ALGOLIA_API_KEY=your_admin_api_key bundle exec jekyll algolia
   ```

   For Windows users you will have to use `set` to assigned the `ALGOLIA_API_KEY` environment variable.

   ```
   set ALGOLIA_API_KEY=your_admin_api_key
   bundle exec jekyll algolia
   ```

   Note that `ALGOLIA_API_KEY` should be set to your admin API key.

To use the Algolia search with GitHub Pages hosted sites follow [this deployment guide](https://community.algolia.com/jekyll-algolia/github-pages.html). Or this guide for [deploying on Netlify](https://community.algolia.com/jekyll-algolia/netlify.html).

**备注：** The Jekyll Algolia plugin can be configured in several ways. Be sure to check out [their full documentation](https://community.algolia.com/jekyll-algolia/options.html "Algolia configuration") on how to exclude files and other valuable settings.
{: .notice--info}

#### Google Custom Search Engine

Add a Google search box to your site.

1. Create a **New search engine** in [Google Custom Search Engine](https://cse.google.com/cse/all), give it an appropriate name and setup "Sites to search" to your liking.

2. Under **Look and feel** choose the "Results only" layout and a theme (*Minimalist* is a good choice to match the default look of the Minimal Mistakes).

   ![Google Custom Search Engine layout]({{ '/assets/images/google-custom-search-engine-layout.png' | relative_url }})

3. Select "Save & Get Code" and grab your search engine ID from the line that begins with `var cx = 'YOUR_SEARCH_ENGINE_ID'`.

4. Add your search engine ID to `_config.yml` like so:

   ```yaml
   google:
     search_engine_id: YOUR_SEARCH_ENGINE_ID
   ```

**备注：** If your site is new and hasn't been indexed by Google yet, search will be incomplete and won't provide accurate results.
{: .notice--info}

### SEO, social sharing, and analytics settings

All optional, but a good idea to take the time setting up to improve SEO and links shared from the site.

#### Google Search Console

Formerly known as [Google Webmaster Tools](https://www.google.com/webmasters/tools/), add your [verification code](https://support.google.com/analytics/answer/1142414?hl=en) like so: `google_site_verification: "yourVerificationCode"`.

**备注：** You likely won't have to do this if you verify site ownership through **Google Analytics** instead.
{: .notice--warning}

#### Bing Webmaster Tools

There are several ways to [verify site ownership](https://www.bing.com/webmasters/help/add-and-verify-site-12184f8b) --- the easiest adding an authentication code to your config file.

Copy and paste the string inside of `content`:

```html
<meta name="msvalidate.01" content="0FC3FD70512616B052E755A56F8952D" />
```

Into `_config.yml`

```yaml
bing_site_verification: "0FC3FD70512616B052E755A56F8952D"
```

#### Naver Webmaster Tools

To verify site ownership you will need to [create a Naver account](https://nid.naver.com/user2/joinGlobal.nhn?lang=en_US&m=init) and then **Add your site** via [Naver Webmaster Tools](http://webmastertool.naver.com/).

Much like Google and Bing you'll be provided with a meta description:

```html
<meta name="naver-site-verification" content="6BF5A01C0E650B479B612AC5A2184144">`
```

Which you can add to your `_config.yml` like so:

```yaml
naver_site_verification: "6BF5A01C0E650B479B612AC5A2184144"
```

#### Yandex

To verify site ownership copy and paste the string inside of `content`:

```html
<meta name='yandex-verification' content='2132801JL' />
```

Into `_config.yml`

```yaml
yandex_site_verification: "2132801JL"
```

#### Baidu

There are several ways to verify site ownership — the easiest is adding an authentication code to your config file.

Copy and paste the string inside of `content`:

```html
<meta name="baidu-site-verification" content="code-iA0wScWXN1" />
```

Into `_config.yml`

```yaml
baidu_site_verification: "code-iA0wScWXN1"
```

#### Twitter Cards and Facebook Open Graph

To improve the appearance of links shared from your site to social networks like Twitter and Facebook be sure to configure the following.

##### Site Twitter username

Twitter username for the site. For pages that have custom author Twitter accounts assigned in their YAML Front Matter or data file, they will be attributed as a **creator** in the Twitter Card.

For example if my site's Twitter account is `@mmistakes-theme` I would add the following to `_config.yml`

```yaml
twitter:
  username: "mmistakes-theme"
```

And if I assign `@mmistakes` as an author account it will appear in the Twitter Card along with `@mmistakes-theme`, attributed as a creator of the page being shared.

**Note**: You need to validate cards are working and have Twitter [approve Player Cards](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/player-card) before they will begin showing up.
{: .notice--warning}

##### Facebook Open Graph

If you have a Facebook ID or publisher page add them:

```yaml
facebook:
  app_id:  # A Facebook app ID
  publisher:  # A Facebook page URL or ID of the publishing entity
```

While not part a part of Open Graph, you can also add your Facebook username for use in the sidebar and footer.

```yaml
facebook:
  username: "michaelrose"  # https://www.facebook.com/michaelrose
```

**专家提醒：** To debug Open Graph data use [this tool](https://developers.facebook.com/tools/debug/) to test your pages. If content changes aren't reflected you will probably have to hit the **Scrape Again** button to refresh.
{: .notice--info}

##### Open Graph default image

For pages that don't have a `header.image` assigned in their YAML Front Matter, `site.og_image` will be used as a fallback. Use your logo, icon, avatar or something else that is meaningful. Just make sure it is placed in the `/assets/images/` folder, has a minimum size of 120px by 120px, and is less than 1MB in file size.

```yaml
og_image: /assets/images/site-logo.png
```

<figure>
  <img src="{{ '/assets/images/mm-twitter-card-summary-image.jpg' | relative_url }}" alt="Twitter Card summary example">
  <figcaption>Example of a image placed in a Summary Card.</figcaption>
</figure>

Documents who have a `header.image` assigned in their YAML Front Matter will appear like this when shared on Twitter and Facebook.

<figure>
  <img src="{{ '/assets/images/mm-twitter-card-summary-large.jpg' | relative_url }}" alt="page shared on Twitter">
  <figcaption>Shared page on Twitter with header image assigned.</figcaption>
</figure>

<figure>
  <img src="{{ '/assets/images/facebook-share-example.jpg' | relative_url }}" alt="page shared on Facebook">
  <figcaption>Shared page on Facebook with header image assigned.</figcaption>
</figure>

##### Include your social profile in search results

Use markup on your official website to add your [social profile information](https://developers.google.com/structured-data/customize/social-profiles#adding_structured_markup_to_your_site) to the Google Knowledge panel in some searches. Knowledge panels can prominently display your social profile information.

```yaml
social:
  type:  # Person or Organization (defaults to Person)
  name:  # If the user or organization name differs from the site's name
  links:
    - "https://twitter.com/yourTwitter"
    - "https://www.facebook.com/yourFacebook"
    - "https://instagram.com/yourProfile"
    - "https://www.linkedin.com/in/yourprofile"
```

#### Analytics

Analytics is disabled by default. To enable globally select one of the following:

| Name                 | Analytics Provider                                              |
| -------------------- | --------------------------------------------------------------- |
| **google**           | [Google Standard Analytics](https://www.google.com/analytics/)  |
| **google-universal** | [Google Universal Analytics](https://www.google.com/analytics/) |
| **google-gtag**      | [Google Analytics Global Site Tag](https://www.google.com/analytics/) |
| **custom**           | Other analytics providers                                       |

For Google Analytics add your Tracking Code:

```yaml
analytics:
  provider: "google-gtag"
  google:
    tracking_id: "UA-1234567-8"
    anonymize_ip: false # default
```

To use another provider not included with the theme set `provider: "custom"` then add their embed code to `_includes/analytics-providers/custom.html`.

**备注：** Analytics are disabled by default in `development`. To enable when testing/building locally be sure to set
`JEKYLL_ENV=production` to [force the environment](http://jekyllrb.com/docs/configuration/#specifying-a-jekyll-environment-at-build-time) to production.
{: .notice--info}

## 站点作者

Used as the defaults for defining what appears in the author sidebar.

![author sidebar example]({{ "/assets/images/mm-author-sidebar-example.jpg" | relative_url }})

**备注：** For sites with multiple authors these values can be overridden post by post with custom YAML Front Matter and a data file. For more information on how that works see below.
{: .notice--info}

```yaml
author:
  name     : "Your Name"
  avatar   : "/assets/images/bio-photo.jpg"
  bio      : "My awesome biography constrained to a sentence or two goes here."
  location : "Somewhere, USA"
```

Author links are all optional, include the ones you want visible under the `author.links` array.

| Name | Description |
| --- | --- |
| **label** | Link label (e.g. `"Twitter"`) |
| **icon** | [Font Awesome icon](https://fontawesome.com/v5/search) classes (e.g. `"fab fa-fw fa-twitter-square"`) |
| **url** | Link URL (e.g. `"https://twitter.com/mmistakes"`) |

```yaml
author:
  name: "Your Name"
  avatar: "/assets/images/bio-photo.jpg"
  bio: "I am an **amazing** person." # 备注： Markdown is allowed
  location: "Somewhere"
  links:
    - label: "Made Mistakes"
      icon: "fas fa-fw fa-link"
      url: "https://mademistakes.com"
    - label: "Twitter"
      icon: "fab fa-fw fa-twitter-square"
      url: "https://twitter.com/mmistakes"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/mmistakes"
    - label: "Instagram"
      icon: "fab fa-fw fa-instagram"
      url: "https://instagram.com/mmistakes"
```

To customize the author sidebar, read the full [layout documentation]({{ "/docs/layouts/#author-profile" | relative_url }}).

## 站点 Footer

Footer links can be added under the `footer.links` array.

| Name | Description |
| --- | --- |
| **label** | Link label (e.g. `"Twitter"`) |
| **icon** | [Font Awesome icon](https://fontawesome.com/v5/search) classes (e.g. `"fab fa-fw fa-twitter-square"`) |
| **url** | Link URL (e.g. `"https://twitter.com/mmistakes"`) |

```yaml
footer:
  links:
    - label: "Twitter"
      icon: "fab fa-fw fa-twitter-square"
      url: "https://twitter.com/mmistakes"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/mmistakes"
    - label: "Instagram"
      icon: "fab fa-fw fa-instagram"
      url: "https://instagram.com/mmistakes"
```

**备注：** Twitter and Facebook footer links no longer automatically pull from `site.twitter.username` and `site.facebook.username`. This behavior has been deprecated in favor of the `footer.links` array above.
{: .notice--danger}

To change "Follow:" text that precedes footer links, edit the `follow_label` key in `_data/ui-text.yml`.

## 阅读文件

Nothing out of the ordinary here. `include` and `exclude` may be the only things you need to alter.

## Conversion and Markdown processing

Again nothing out of the ordinary here as the theme adheres to the defaults used by GitHub Pages. [**Kramdown**](http://kramdown.gettalong.org/) for Markdown conversion, [**Rouge**](http://rouge.jneen.net/) syntax highlighting, and incremental building disabled. Change them if you need to.

## Front Matter 默认值

To save yourself time setting [Front Matter Defaults](https://jekyllrb.com/docs/configuration/front-matter-defaults/) for posts, pages, and collections is the way to go. Sure you can assign layouts and toggle settings like **reading time**, **comments**, and **social sharing** in each file, but that's not ideal.

Using the `default` key in `_config.yml` you could set the layout and enable author profiles, reading time, comments, social sharing, and related posts for all posts --- in one shot.

```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
```

Pages Front Matter defaults can be scoped like this:

```yaml
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
```

And collections like this:

```yaml
defaults:
  # _foo
  - scope:
      path: ""
      type: foo
    values:
      layout: single
```

And of course any default value can be overridden by settings in a post, page, or collection file. All you need to do is specify the settings in the YAML Front Matter. For more examples be sure to check out the demo site's [`_config.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml).

## 输出

The default permalink style used by the theme is `permalink: /:categories/:title/`. If you have a post named `2016-01-01-my-post.md` with `categories: foo` in the YAML Front Matter, Jekyll will generate `_site/foo/my-post/index.html`.

**备注：** If you plan on enabling breadcrumb links --- including category names in permalinks is a big part of how those are created.
{: .notice--warning}

### 分页

If [using pagination](https://github.com/jekyll/jekyll-paginate) on the homepage you can change the amount of posts shown with:

```yaml
paginate: 5
```

You'll also need to include some Liquid and HTML to properly use the paginator, which you can find in the **Layouts** section under [Home Page]({{ "/docs/layouts/#home-page" | relative_url }}).

The paginator only works on files with name `index.html`. To use pagination in a subfolder --- for example `/recent/`, create `/recent/index.html` and set the `paginate_path` in `_config.yml` to this:

```yaml
paginate_path: /recent/page:num/
```

**Please 备注：** When using Jekyll's default [pagination plugin](https://jekyllrb.com/docs/pagination/) `paginator.posts` can only be called once. If you're looking for something more powerful that can paginate category, tag, and collection pages I suggest [**jekyll-paginate-v2**](https://github.com/sverrirs/jekyll-paginate-v2).
{: .notice--info}

### 时区

This sets the timezone environment variable, which Ruby uses to handle time and date creation and manipulation. Any entry from the [IANA Time Zone Database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) is valid. The default is the local time zone, as set by your operating system.

```yaml
timezone: America/New_York
```

## 插件

When hosting with GitHub Pages a small [set of gems](https://pages.github.com/versions/) have been whitelisted for use. The theme uses a few of them which can be found under `gems`. Additional settings and configurations are documented in the links below.

| Plugin | Description                                                                               |
| --- | --- |
| [jekyll-paginate][jekyll-paginate] | Pagination Generator for Jekyll. |
| [jekyll-sitemap][jekyll-sitemap] | Jekyll plugin to silently generate a sitemaps.org compliant sitemap for your Jekyll site. |
| [jekyll-gist][jekyll-gist] | Liquid tag for displaying GitHub Gists in Jekyll sites. |
| [jekyll-feed][jekyll-feed] | A Jekyll plugin to generate an Atom (RSS-like) feed of your Jekyll posts. |
| [jekyll-include-cache][jekyll-include-cache] | Liquid tag that caches Liquid includes. |

[jekyll-paginate]: https://github.com/jekyll/jekyll-paginate
[jekyll-sitemap]: https://github.com/jekyll/jekyll-sitemap
[jekyll-gist]: https://github.com/jekyll/jekyll-gist
[jekyll-feed]: https://github.com/jekyll/jekyll-feed
[jekyll-include-cache]: https://github.com/benbalter/jekyll-include-cache

If you're hosting elsewhere then you don't really have to worry about what is whitelisted as you are free to include whatever [Jekyll plugins](https://jekyllrb.com/docs/plugins/) you desire.

**备注：** The [jekyll-include-cache](https://github.com/benbalter/jekyll-include-cache) plugin needs to be installed in your `Gemfile` and added to the `plugins` array of `_config.yml`. Otherwise you'll throw `Unknown tag 'include_cached'` errors at build.
{: .notice--warning}

## 归档设置

The theme ships with support for taxonomy (category and tag) pages. GitHub Pages hosted sites need to use a _Liquid only_ approach while those hosted elsewhere can use plugins like [**jekyll-archives**][jekyll-archives] to generate these pages automatically.

[jekyll-archives]: https://github.com/jekyll/jekyll-archives

The default `type` is set to use Liquid.

**备注：** `category_archive` and `tag_archive` were previously named `categories` and `tags`. Names were changed to avoid possible conflicts with `site.categories` and `site.tags`.
{: .notice--danger}

```yaml
category_archive:
  type: liquid
  path: /categories/
tag_archive:
  type: liquid
  path: /tags/
```

Which would create category and tag links in the breadcrumbs and page meta like: `/categories/#foo` and `/tags/#foo`.

**备注：** these are simply hash (fragment) links into the full taxonomy index pages. For them to resolve properly, the category and tag index pages need to exist at [`/categories/index.html`](https://github.com/{{ site.repository }}/blob/master/docs/_pages/category-archive.md) (copy to `_pages/category-archive.md`) and [`/tags/index.html`](https://github.com/{{ site.repository }}/blob/master/docs/_pages/tag-archive.md) (copy to `_pages/tag-archive.md`).
{: .notice--warning}

If you have the luxury of using Jekyll Plugins, then [**jekyll-archives**][jekyll-archives] will create a better experience as discrete taxonomy pages would be generated, and their corresponding links would be "real" (not just hash/fragment links into a larger index). However, the plugin will not generate the taxonomy index pages (`category-archive.md` and `tag-archive.md`) so you'd still need to manually create them if you'd like to have them (see note above).

First, you'll need to make sure that the `jekyll-archives` plugin is installed. Either run `gem install jekyll-archives` or add the following to your `Gemfile`:

```
group :jekyll_plugins do
  gem "jekyll-archives"
end
```

Then run `bundle install`.

Now that the plugin is installed, change `type` to `jekyll-archives` and apply the following [configurations](https://github.com/jekyll/jekyll-archives/blob/master/docs/configuration.md):

```yaml
category_archive:
  type: jekyll-archives
  path: /categories/
tag_archive:
  type: jekyll-archives
  path: /tags/
jekyll-archives:
  enabled:
    - categories
    - tags
  layouts:
    category: archive-taxonomy
    tag: archive-taxonomy
  permalinks:
    category: /categories/:name/
    tag: /tags/:name/
```

**备注：** The `archive-taxonomy` layout used by jekyll-archives is provided with the theme and can be found in the `_layouts` folder.
{: .notice--info}

<div class="notice--success" markdown="1">

<h4 class="no_toc"><i class="fas fa-lightbulb"></i> Tip</h4>

To apply [Front Matter defaults](https://jekyllrb.com/docs/configuration/front-matter-defaults/) to pages generated by the `jekyll-archives` plugin, you can specify a scope of an empty `path` and a `type` of either `tag` or `category`.

For example, the following configuration enables author profile on tag archives and disables comments on category archives.

```yaml
defaults:
  - scope:
      path: ""
      type: tag
    values:
      author_profile: true
  - scope:
      path: ""
      type: category
    values:
      comments: false
```

</div>

## HTML 压缩

If you care at all about performance (and really who doesn't) compressing the HTML files generated by Jekyll is a good thing to do.

If you're hosting with GitHub Pages there aren't many options afforded to you for optimizing the HTML Jekyll generates. Thankfully there is some Liquid wizardry you can use to strip whitespace and comments to reduce file size.

There's a variety of configurations and caveats to using the `compress` layout, so be sure to read through the [documentation](http://jch.penibelst.de/) if you decide to make change the defaults set in the theme's `_config.yml`.

```yaml
compress_html:
  clippings: all
  ignore:
    envs: development  # disable compression in dev environment
```

**Caution:** Inline JavaScript comments can cause problems with `compress.html`, so be sure to `/* comment this way */` and avoid `// these sorts of comments`.
{: .notice--warning}

**备注：** CDN services such as CloudFlare provide optional automatic minification for HTML, CSS, and JavaScript. If you are serving your site via such a service and have minification enabled, this configuration might be redundant.
{: .notice--info}
