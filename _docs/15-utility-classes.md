---
title: "工具类"
permalink: /docs/utility-classes/
excerpt: "CSS classes for aligning text/image, styling buttons and notices, and more."
last_modified_at: 2018-11-25T19:46:43-05:00
toc: true
toc_label: "工具类"
toc_icon: "cogs"
---

在 Jekyll 使用 kramdown Markdown 渲染器可以添加[块](http://kramdown.gettalong.org/quickref.html#block-attributes)和[行内属性](http://kramdown.gettalong.org/quickref.html#inline-attributes)。如果您想用 Markdown 为文字和图像添加定制的样式是很好的。

**Jekyll 3：** kramdown 是 `jekyll new` 生成站点和托管于 GitHub Pages 的站点的默认格式。不想使用 kramdown？当然也可以。下列类在您使用标准 HTML 时都是可以使用的。
{: .notice--warning}

## 文本对齐

使用下列类对齐文本块。

文本左对齐。 `.text-left`
{: .text-left}

```markdown
Left aligned text
{: .text-left}
```

---

文本居中。 `.text-center`
{: .text-center}

```markdown
Center aligned text.
{: .text-center}
```

---

文本右对齐。 `.text-right`
{: .text-right}

```markdown
Right aligned text.
{: .text-right}
```

---

**Justified text.** `.text-justify` Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vel eleifend odio, eu elementum purus. In hac habitasse platea dictumst. Fusce sed sapien eleifend, sollicitudin neque non, faucibus est. Proin tempus nisi eu arcu facilisis, eget venenatis eros consequat.
{: .text-justify}

```markdown
Justified text.
{: .text-justify}
```

---

No wrap text. `.text-nowrap`
{: .text-nowrap}

```markdown
No wrap text.
{: .text-nowrap}
```

## 图像对齐

Position images with the following classes.

![image-center]({{ "/assets/images/image-alignment-580x300.jpg" | relative_url }}){: .align-center}

The image above happens to be **centered**.

```markdown
![image-center](/assets/images/filename.jpg){: .align-center}
```

---

![image-left]({{ "/assets/images/image-alignment-150x150.jpg" | relative_url }}){: .align-left} The rest of this paragraph is filler for the sake of seeing the text wrap around the 150×150 image, which is **left aligned**. There should be plenty of room above, below, and to the right of the image. Just look at him there --- Hey guy! Way to rock that left side. I don't care what the right aligned image says, you look great. Don't let anyone else tell you differently.

```markdown
![image-left](/assets/images/filename.jpg){: .align-left}
```

---

![image-right]({{ "/assets/images/image-alignment-300x200.jpg" | relative_url }}){: .align-right}

And now we're going to shift things to the **right align**. Again, there should be plenty of room above, below, and to the left of the image. Just look at him there --- Hey guy! Way to rock that right side. I don't care what the left aligned image says, you look great. Don't let anyone else tell you differently.

```markdown
![image-right](/assets/images/filename.jpg){: .align-right}
```

---

![full]({{ "/assets/images/image-alignment-1200x4002.jpg" | relative_url }})
{: .full}

The image above should extend outside of the parent container on right.

```markdown
![full](/assets/images/filename.jpg)
{: .full}
```

## 按钮

Make any link standout more when applying the `.btn .btn--primary` classes.

```html
<a href="#" class="btn btn--primary">Link Text</a>
```

| Button Type   | Example | Class | Kramdown |
| ------        | ------- | ----- | ------- |
| Default       | [Text](#link){: .btn} | `.btn` | `[Text](#link){: .btn}` |
| Primary       | [Text](#link){: .btn .btn--primary} | `.btn .btn--primary` | `[Text](#link){: .btn .btn--primary}` |
| Success       | [Text](#link){: .btn .btn--success} | `.btn .btn--success` | `[Text](#link){: .btn .btn--success}` |
| Warning       | [Text](#link){: .btn .btn--warning} | `.btn .btn--warning` | `[Text](#link){: .btn .btn--warning}` |
| Danger        | [Text](#link){: .btn .btn--danger} | `.btn .btn--danger` | `[Text](#link){: .btn .btn--danger}` |
| Info          | [Text](#link){: .btn .btn--info} | `.btn .btn--info` | `[Text](#link){: .btn .btn--info}` |
| Inverse       | [Text](#link){: .btn .btn--inverse} | `.btn .btn--inverse` | `[Text](#link){: .btn .btn--inverse}` |
| Light Outline | [Text](#link){: .btn .btn--light-outline} | `.btn .btn--light-outline` | `[Text](#link){: .btn .btn--light-outline}` |

| Button Size | Example | Class | Kramdown |
| ----------- | ------- | ----- | -------- |
| X-Large     | [X-Large Button](#){: .btn .btn--primary .btn--x-large} | `.btn .btn--primary .btn--x-large` | `[Text](#link){: .btn .btn--primary .btn--x-large}` |
| Large       | [Large Button](#){: .btn .btn--primary .btn--large} | `.btn .btn--primary .btn--large` | `[Text](#link){: .btn .btn--primary .btn--large}` |
| Default     | [Default Button](#){: .btn .btn--primary} | `.btn .btn--primary` | `[Text](#link){: .btn .btn--primary }` |
| Small       | [Small Button](#){: .btn .btn--primary .btn--small} | `.btn .btn--primary .btn--small` | `[Text](#link){: .btn .btn--primary .btn--small}` |

## 通知

引起注意的文本块。

| 通知类型    | 类                 |
| ----------- | -----              |
| Default     | `.notice`          |
| Primary     | `.notice--primary` |
| Info        | `.notice--info`    |
| Warning     | `.notice--warning` |
| Success     | `.notice--success` |
| Danger      | `.notice--danger`  |

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice}` class.
{: .notice}

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--primary}` class.
{: .notice--primary}

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--info}` class.
{: .notice--info}

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--warning}` class.
{: .notice--warning}

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--success}` class.
{: .notice--success}

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--danger}` class.
{: .notice--danger}

{% capture notice-text %}
You can also add the `.notice` class to a `<div>` element.

* Bullet point 1
* Bullet point 2
{% endcapture %}

<div class="notice--info">
  <h4 class="no_toc">Notice Headline:</h4>
  {{ notice-text | markdownify }}
</div>
