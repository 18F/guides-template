---
permalink: /updating-the-config-file/understanding-baseurl/
title: Understanding the `baseurl:` property
parent: Updating the config file
---
The `baseurl:` configuration property affects the root URL of your guide when
served locally on your machine. When published on [18F
Pages](https://pages.18f.gov/), the `baseurl:` is set automatically to the
name of your repository, so you don't have to set it yourself.

For example, when run locally, the URL for this guide is
`http://localhost:4000/`. In production, the URL is
`https://pages.18f.gov/guides-template/`.

The URLs of the individual section pages are relative to the `baseurl:`. For
example, the `permalink:` of this page is `{{page.permalink}}`. The full local
URL is `http://localhost:4000{{page.permalink}}`, and in
production it is `https://pages.18f.gov/guides-template{{page.permalink}}`.

### Links to other pages within the guide

Every link to another page within the same guide _must_ be prefixed with
`{% raw %}{{ site.baseurl }}{% endraw %}`, even if you do not set `baseurl:` yourself. For example,
this link to [Adding a new page]({{ site.baseurl }}/adding-a-new-page/)
appears in the Markdown source as:
```
{% raw %}[Adding a new page]({{ site.baseurl }}/adding-a-new-page/){% endraw %}.
```

### Changing the `baseurl:` when serving locally

If you you do change the `baseurl:` property in the `_config.yml` file,
**remember to include the trailing '`/`' when serving locally**. The Jekyll
built-in webserver doesn't redirect to it automatically.


