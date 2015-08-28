---
permalink: /
title: Introduction
---
This is the template used to create [18F Guides](http://pages.18f.gov/guides/)
and other 18F-branded documentation available on [18F
Pages](https://pages.18f.gov/). It's structured to act as an 18F Guides guide,
walking you through how to create and publish an 18F Pages document based on
the same theme.

The template is derived from [CFPB/DOCter](https://github.com/CFPB/DOCter).
It uses [Jekyll](http://jekyllrb.com/) as the rendering engine.

## Creating a new guide/document

To create a brand new guide (or other document based on this theme), first
follow [the "Getting started" instructions in the 18F/guides-template GitHub
repository](https://github.com/18F/guides-template/#getting-started) to create
a local clone of this template.

Once you've created a new clone, click the _Adding a New Page_ entry in the
table of contents.

## Updating an existing guide/document

__Note: You only need to do this if your existing document is not already
using the `guides_style_18f` gem or if it does not have an `18f-pages`
branch.__

Add the [`guides_style_18f` gem](https://github.com/18F/guides-style) to your
Guide's `Gemfile` if it's not already present. You may also wish to copy the
`./go` script from the template if your document doesn't already have one.

To receive layout updates, as well as any new styles or scripts associated
with them, you will need to run `./go update_theme`. (Or, if you aren't using
a `./go` script, you can run `bundle update --source guides_style_18f`
manually.)

If your repository already has a `gh-pages` branch, you can create an
`18f-pages` branch from it by running these commands:

```
$ git checkout -b 18f-pages gh-pages
$ git push origin 18f-pages
```

Follow the instructions in _Updating the Config File_ to update your
`_config.yml` accordingly. You may also need to consult the _GitHub Setup_ and
_Post Your Guide_ chapters to ensure your guide is correctly published to
`pages.18f.gov` and linked from the main [18F
Guides](http://pages.18f.gov/guides/) site.
