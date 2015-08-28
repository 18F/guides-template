## 18F Guides Template

This is a skeleton repo containing the
[CFPB/DOCter](https://github.com/CFPB/DOCter)-based
[Jekyll](http://jekyllrb.com/) template for
[18F Guides](http://18f.github.io/guides/).

### Getting started

#### Installing Ruby

You will need [Ruby](https://www.ruby-lang.org) ( > version 2.1.5 ). You may
consider using a Ruby version manager such as
[rbenv](https://github.com/sstephenson/rbenv) or [rvm](https://rvm.io/) to
help ensure that Ruby version upgrades don't mean all your
[gems](https://rubygems.org/) will need to be rebuilt.

On OS X, you can use [Homebrew](http://brew.sh/) to install Ruby in
`/usr/local/bin`, which may require you to update your `$PATH` environment
variable:

```shell
$ brew update
$ brew install ruby
```

#### Cloning and serving the Guides Template locally

To create a new guide and serve it locally, where `MY-NEW-GUIDE` is the name
of your new repository:

```shell
$ git clone https://github.com/18F/guides-template.git MY-NEW-GUIDE
$ cd MY-NEW-GUIDE
$ ./go serve
```

The `./go` script will check that your Ruby version is supported, install the
[Bundler gem](http://bundler.io/) if it is not yet installed, install all the
gems needed by the template, and launch a running instance on
`http://localhost:4000/`.

#### Follow the template instructions

The Guides Template (either [running locally](http://localhost:4000) or the
[published version](https://pages.18f.gov/guides-template/) will walk you
through the rest of the steps to edit and publish your guide.

### Staging version (for 18F team members)

In addition to the `18f-pages` branch, you can create an `18f-pages-staging`
branch and changes to that branch will be published to
`https://pages-staging.18f.gov/MY-NEW-GUIDE`, which is identical to
`https://pages.18f.gov/` but provides authenticated access.

### Public domain

This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be released under the CC0
>dedication. By submitting a pull request, you are agreeing to comply
>with this waiver of copyright interest.
