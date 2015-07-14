---
permalink: /adding-a-new-page/making-a-child-page/
layout: default
title: Making a Child Page
parent: Adding a New Page
---

If you want to nest a page under a parent page, follow the instructions to [add a new page](/adding-a-new-page/) with two additions to the YAML front matter. Here is the front-matter for this page:

```yaml
---
permalink: /adding-a-new-page/making-a-child-page/
layout: default
title: Making a Child Page
parent: Adding a New Page
---
```

Note the `/parent/child/` format for the permalink, and the `parent:` property. This way, when you're on a parent or child page, the children will be visible in the menu.

Now to add it to the site nav, update `site.navigation` like so:

```yaml
navigation:
- text: Introduction
  url: index.html
  internal: true
- text: Adding a New Page
  url: adding-a-new-page/
  internal: true
  children:
    - text: Making a Child Page
      url: making-a-child-page/
      internal: true
```