---
title: Advanced features
---
These features are not necessary to produce a guide, but are available if you
need them.

### Checking the build log

If your site did not rebuild after pushing an update, see the latest build log
on Federalist. Go to [federalist.18f.gov](https://federalist.18f.gov). Login
and select your site from the list of sites. Then select "builds" from the
sidebar.

### Branch previews

When you push a new branch to GitHub, Federalist will build a preview of that
branch. To see branch previews, login at
[federalist.18f.gov](https://federalist.18f.gov) and select your guide from the
list of sites. Select "Settings" in the sidebar and you'll see a table of all of
the branches Federalist knows about. There you have the option to view a preview
of a given branch.

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


