---
permalink: /adding-a-new-page/making-a-child-page/
title: Making a child page
parent: Adding a new page
---

If you want to nest a page under a parent page, follow the instructions to [add a new page]({{ site.baseurl }}/adding-a-new-page/) with two additions to the YAML front matter. Here is the front-matter for this page:

```yaml
---
permalink: {{ page.permalink }}
title: {{ page.title }}
parent: {{ page.parent }}
---
```

Note the `/parent/child/` format for the permalink, and the `parent:`
property. This way, when you're on a parent or child page, the children will
be visible in the menu. (You will need to
[run `./go update_nav`]({{ site.baseurl }}/updating-the-config-file/#register-new-pages)
before the changes to the menu will appear, as explained in the _Updating the
config file_ chapter.)

## Next steps

Now click on the _Adding images_ entry in the table of contents to learn how
to add images to your guide.
