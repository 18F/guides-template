---
permalink: /updating-the-config-file/understanding-baseurl/
title: Understanding the `baseurl:` property
parent: Updating the config file
---
__It is not necessary to update `baseurl:` yourself in most cases. This
section is not necessary to follow through with the reset of the
instructions.__

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

## Changing the `baseurl:` when serving locally

If you you do change the `baseurl:` property in the `_config.yml` file,
**remember to include the trailing '`/`' when serving locally**. The Jekyll
built-in webserver doesn't redirect to it automatically.
