---
permalink: /add-a-new-page/
title: Add a new page
---
To add new pages to the guide, first create a new
[Markdown](http://daringfireball.net/projects/markdown/syntax) file in the
`pages/` directory of the repository. As an example, the Markdown text for
this page is
[`pages/new-page.md`](https://github.com/18F/guides-template/blob/18f-pages/pages/new-page.md).

The Markdown document begins with this [YAML front
matter](http://jekyllrb.com/docs/frontmatter/):

```yaml
---
permalink: {{ page.permalink }}
title: {{ page.title }}
---
```

**The '`/`' at the end of the `permalink:` attribute is important!** It
ensures the page is generated as `{{ page.permalink }}index.html`. Without it,
it would be generated as
`{{ page.permalink | remove_first: '/' | replace:'/','.'}}html`.

## Links to other pages within the guide

Every link to another page within the same guide _must_ be prefixed with
`{% raw %}{{ site.baseurl }}{% endraw %}`. For example,
this link to [Adding images]({{ site.baseurl }}/adding-images/)
appears in the Markdown source as:

```
{% raw %}[Adding images]({{ site.baseurl }}/adding-images/){% endraw %}.
```

## Next steps

Click on the _Adding images_ entry in the table of contents to learn how
to add images to your guide, or click on _Making a child page_ to see how to
make chapters appear as children of related chapters.
