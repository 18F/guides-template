---
permalink: /updating-the-config-file/
title: Updating the config file
---
- [Set the guide name](#set-name)
- [Copy the `exclude:` entries](#copy-exclude-entries)
- [Register new pages](#register-new-pages)
- [Update the repository list](#update-repository-list)
- [Set `google_analytics_ua`](#set-google-analytics)

Once you're finished updating the config file, click the _GitHub Setup_
entry in the table of contents.

## <a name="set-name"></a>Set the guide name

The configuration file is called `_config.yml`. Update the `name:` property,
which appears as the guide's overall title. You may also set the `baseurl:`
property, which affects the root URL of your guide when served locally on your
machine. When published on [18F Pages](https://pages.18f.gov/), the `baseurl:`
is set automatically to the name of your repository, so you don't have to set
it yourself.

For example, for this template, these values are set to:

```yaml
name: {{site.name}}
baseurl: {{site.baseurl}}
```

When run locally, the URL for this guide is
`http://localhost:4000{{site.baseurl}}/`. **Remember to include the trailing
`/` when serving locally** if you change the `baseurl:` property in the
`_config.yml` file. The Jekyll built-in webserver doesn't redirect to it
automatically.

The URLs of the individual section pages are relative to the `baseurl:`. For
example, the `permalink:` of this page is `{{page.permalink}}`. The full local
URL is `http://localhost:4000{{site.baseurl}}{{page.permalink}}`.

## <a name="copy-exclude-entries"></a>Copy the `exclude:` entries

Make sure that you update the `exclude:` list to contain at least the
following files so that they are not copied to your generated `_site`
directory:

```yaml
exclude:
{% for i in site.exclude %}- {{ i }}
{% endfor %}```

## <a name="register-new-pages"></a>Register new pages

The `navigation:` list is used to generate the table of contents. Add a new
entry for any new page added.

You can run `./go update_nav` from the root directory to do this automatically
(and run it again whenever you add pages or make `title:`, `permalink:`, or
`parent:` changes), but you may want to edit the results by hand to produce
the desired ordering of pages.

For example, the `navigation:` section of this guide contains:

```yaml
navigation:
{% for i in site.navigation %}- text: {{ i.text }}
  url: {{ i.url }}
  internal: {{ i.internal }}{% if i.children %}
  children:{% for child in i.children %}
  - text: {{ child.text }}
    url: {{ child.url }}
    internal: {{ child.internal }}{% endfor %}{% endif %}
{% endfor %}```

## <a name="update-repository-list"></a>Update the repository list

You will also need to update the `repos:` list to reflect the GitHub
repository containing your guide. The `repos:` entry of this template
contains:

```yaml
repos:{% for i in site.repos %}
- name: {{ i.name }}
  description: {{ i.description }}
  url: {{ i.url }}
{% endfor %}
```

## <a name="set-google-analytics"></a>Set `google_analytics_ua`

Set `google_analytics_ua` to the following, if it isn't set already:

```yaml
google_analytics_ua: {{ site.google_analytics_ua }}
```
