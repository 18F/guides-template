---
title: Advanced features
---
These features are not necessary to produce a guide, but are available if you
need them.

### Checking the build log

If your site did not rebuild after pushing an update, see the latest build log
at `https://pages.18f.gov/MY-SITE/build.log`, where `MY-SITE` is the name of
your Guide's repository. For example, the latest build log for this site is
[`https://pages.18f.gov/guides-template/build.log`](https://pages.18f.gov/guides-template/build.log).

### Server-generated defaults

The [18F Pages Server](https://www.npmjs.com/package/18f-pages-server) will
generate an additional configuration file, `_config_18f_pages.yml`, that will
contain the following configuration values:

* **baseurl:** This sets `{% raw %}{{ site.baseurl }}{% endraw %}` to the
  repository name without the organization prefix, e.g.  `/guides-template`
  for the `18F/guides-template` repo, resulting in
  `https://pages.18f.gov/guides-template/`. See the
  [Understanding the `baseurl:` property](/update-the-config-file/understanding-baseurl/)
  section for details.
* **asset_root:** This sets the location from which the guide will load its
  CSS and JavaScript assets.

### Understanding `asset_root`

When developing locally, this value is empty, so your assets are loaded from
your local instance. When hosted on `https://pages.18f.gov/`, this value is
set as `/guides-template`. This allows all pages on the host that use this
style template to receive CSS and JavaScript updates automatically whenever
`https://pages.18f.gov/guides-template` is updated.

### Overriding server-generated defaults

If you _really_ want, you can prevent the 18F Pages server from generating its
own configuration by adding a `_config_18f_pages.yml` file to your site. The
18F Pages server will use that file instead of generating its own.

### Additional scripts and styles

If you'd like to add additional scripts or styles to every page on the site,
you can add `styles:` and `scripts:` lists to `_config.yml`. To add them to a
particular page, add these lists to the page's front matter.

### Overriding the theme's built-in styles

To override the built-in styles, create a new file in `assets/css` and add it
to the `scripts:` list in `_config.yml`.

However, consider sending a pull request to update the contents of
[`lib/guides_style_18f/sass/`](https://github.com/18F/guides-style/tree/master/lib/guides_style_18f/sass)
if your changes may be beneficial to all 18F-themed sites.

### Experimenting with the `guides_style_18f` gem

To try out changes to the common 18F theme, clone the [18F/guides-style
repository](https://github.com/18F/guides-style/) into the same parent
directory as your guide. Then update your `Gemfile` to point
`guides_style_18f` to this clone:

```yaml
group :jekyll_plugins do
  gem 'guides_style_18f', path: '../guides-style'
end
```

Then run `bundle install` and `./go serve` to begin using the local version of
`guides_style_18f`. Any changes within your `guides-style` clone will appear
in your locally-hosted guide upon reload.

### Publishing to internal sites

There are several 18F Pages hosts that require OAuth2 authentication to
access. To publish to one of these hosts, push changes to the following
branches:

- **`18f-pages-staging`**: publishes to `https://pages-staging.18f.gov/`
- **`18f-pages-internal`**: publishes to `https://pages-internal.18f.gov/`
- **`18f-pages-dev`**: publishes to `https://pages-dev.18f.gov/`

There is one other internal host, `https://pages-releases.18f.gov/`, which
does something special. If you publish to a branch matching the pattern
`v[0-9]+.[0-9]+.[0-9]*[a-z]+`, your site will appear on this host with
`baseurl` set to `REPOSITORY/BRANCH`. For example, pushing to a branch called
`v0.9.x` within `18F/guides-template` would publish
`https://pages-releases.18f.gov/guides-template/v0.9.x`.

### Publishing to internal and external sites from the same branch

By adding an optional `_config_internal.yml` file to your guide, your site
will appear at `https://pages-internal.18f.gov/` as well as
`https://pages.18f.gov`. If the contents of this file contain:

```yaml
internal: true
```

then you can ensure that sections formatted with the following markup only appear on
`pages-internal.18f.gov`, and are stripped out of the public-facing
`pages.18f.gov`:

<pre>
{% raw %}{% if site.internal %}TEXT TO BE REDACTED FROM PUBLIC PRODUCTION + STAGING{% endif %}{% endraw %}
</pre>

For more details, see the [`18f-pages-server`
README](https://github.com/18F/pages-server#publishing-to-internal-and-external-sites-from-the-same-branch).
