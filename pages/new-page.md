---
permalink: /add-a-new-page/
title: Add a new page
---

To add new pages, create a
[Markdown](http://daringfireball.net/projects/markdown/syntax) file in the
`pages/` directory of the repository. For example, the Markdown text for
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
the page generates as
`{{ page.permalink | remove_first: '/' | replace:'/','.'}}html`.

## Next steps

Click the _Add images_ entry in the table of contents to learn how
to add images to your guide, or click _Make a child page_ to see how to
make chapters appear as children of related chapters.
