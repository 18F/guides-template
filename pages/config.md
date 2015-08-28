---
permalink: /updating-the-config-file/
title: Updating the config file
---
Work your way through these steps as you create a new guide:
- [Set the guide name](#set-name)
- [Copy the `exclude:` entries](#copy-exclude-entries)
- [Register new pages](#register-new-pages)
- [Update the repository list](#update-repository-list)
- [Set `google_analytics_ua`](#set-google-analytics)

Once you're finished updating the config file, click the _GitHub Setup_
entry in the table of contents.

## <a name="set-name"></a>Set the guide name

The configuration file is called `_config.yml`. Update the `name:` property,
which appears as the guide's overall title. For example:

```yaml
name: {{site.name}}
```

## <a name="copy-exclude-entries"></a>Copy the `exclude:` entries

Make sure that you update the `exclude:` list to contain at least the
following files so that they are not copied to your generated `_site`
directory:

```yaml
exclude:
{% for i in site.exclude %}- {{ i }}
{% endfor %}```

## <a name="register-new-pages"></a>Register new pages

The `navigation:` list is used to generate the table of contents. For example,
the `navigation:` section of this guide contains:

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

Run `./go update_nav` from the root directory to update this list
automatically whenever you add pages or make `title:`, `permalink:`, or
`parent:` changes. After running the script, you may want to edit the results
by hand to produce the desired ordering of any new pages; the order of
existing entries will remain the same.

## <a name="update-repository-list"></a>Update the repository list

You will also need to update the `repos:` list to reflect the GitHub
repository containing your guide. The first of these repositories should be
the repository for the guide itself, and will be used to generate the _Edit
this page_ and _file an issue_ links in the footer.

The `repos:` entry of this template contains:

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
