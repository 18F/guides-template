---
title: Post your guide
---
Work your way through these steps to set up automated publishing to [18F
Pages](https://pages.18f.gov/) for your new guide:

- [Add the guide to Federalist](#federalist)
- [Set the `baseurl` configuration for Federalist builds](#set-baseurl)
- [Add the new guide to 18F Guides.](#add-new-guide)

### <a name="federalist"></a>Add the site to Federalist

The first step is to add your guide to [Federalist](https://federalist.18f.gov/).
Federalist will automatically re-build the guide in response to changes in its GitHub repository.

To get started, navigate to [federalist.18f.gov](htttps://federalist.18f.gov)
and login. After you've logged in, click the "Add Website" button.

<img src="{{site.baseurl}}/images/federalist-add-website.png" alt="The button for adding a website to Federalist">

On the next page, enter "18f" in the text field for the "Repository Owner's
Name" and the name of your guide's GitHub repository in the text field for the
"Repository's Name". It is important that you type "18f" with a lowercase "f",
or Federalist will not publish the guide.

<img src="{{site.baseurl}}/images/federalist-add-repository.png" alt="Federalist's interface for adding a new site">

When you click "Submit repository-based site", your guide will be added to
Federalist.

### <a name="set-baseurl"></a>Set the `baseurl` configuration for Federalist builds

Now that Federalist knows about your site, it's time to set the `baseurl`.
Click on your guide in the site list and then select "Settings" from the
sidebar. Scroll down the page until you see a text area for "Custom
Configuration". Here you will set the `baseurl` for your guide.

<img src="{{site.baseurl}}/images/federalist-custom-config.png" alt="Federalist's interface for adding custom configs to a site">

The value of the `baseurl` will be the name of the GitHub repository where your
guide lives.

```yaml
baseurl: my-github-repo-name
```

When the `baseurl` is set, Federalist will post guide to
`https://pages.18f.gov/<your-repo-name>`. This may take up to 5 to 10 minutes.
If you have any difficulty adding your guide, don't hesitate to head over to the
`#federalist-support` Slack channel to ask for help.

### <a name="add-new-guide"></a>Add the new guide to 18F Guides

You've reached the final step! Add an entry to the `navigation:` list of [18F
Guides](https://guides.18f.gov/) linking to your new guide. You can [use
this link to edit the file directly in
GitHub](https://github.com/18F/guides/edit/master/_config.yml):

<img src="{{site.baseurl}}/images/gh-add-guide.png" alt="Add the new guide to 18F Guides using the GitHub text editor">

Congratulations! Your guide should now be published and accessible to the world
as one of the few, the proud, the [18F Guides](https://pages.18f.gov/guides/)!
