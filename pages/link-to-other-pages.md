---
permalink: /link-to-other-pages/
title: Link to other pages
---

## Link to other pages within the guide

Every link to another page _must_ be prefixed with
`{% raw %}{{ site.baseurl }}{% endraw %}`. For example,
this link to [Add images]({{ site.baseurl }}/add-images/)
appears in the Markdown source as:

```
{% raw %}[Add images]({{ site.baseurl }}/add-images/){% endraw %}.
```
