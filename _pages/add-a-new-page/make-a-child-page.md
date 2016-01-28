---
title: Make a child page
---

If you want to nest a page under a parent page, first create a subdirectory of
`_pages` that matches the file name of the parent page, minus the `.md` or
other file extension. For example, the directory containing this page is
{% capture basename %}/{{ page.path | split:"/" | last }}{% endcapture %}{% capture parent_dir %}{{ page.path | replace:basename,'' }}{% endcapture %}[`{{ parent_dir }}`]({{ site.repos[0].url }}/tree/18f-pages/{{ parent_dir }}/).

Then follow the instructions to [add a new page]({{ site.baseurl }}/add-a-new-page/) inside the child directory. Here is the front-matter for this page:

```yaml
---
title: {{ page.title }}
---
```

Or, if the page had set its `permalink:` explicitly:

```yaml
---
permalink: {{ page.url }}
title: {{ page.title }}
---
```

Note the `/parent/child/` format for the permalink. This way, when you're on a
parent or child page, the children are visible in the menu. (You'll need to
[run `./go update_nav`]({{ site.baseurl }}/update-the-config-file/#register-pages-in-nav-bar)
before the changes to the menu appear— read more about that in the _Update the
config file_ chapter.)

### Next steps

Click the _Add images_ entry in the table of contents to learn how to add
images to your guide.
