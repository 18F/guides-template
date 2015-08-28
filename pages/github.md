---
permalink: /github-setup/
title: GitHub setup
---
- [Create a new local repository](#create-local-repo)
- [Create a new 18F GitHub repository](#create-18f-repo)

Once you've finished the steps below to create your new 18F guide repo and
push it to GitHub, click the _Post Your Guide_ entry in the table of contents
for the final steps to publish your guide.

## <a name="create-local-repo"></a>Create a new local repository

Once you've got the `_config.yml` file up-to-date, in the root directory of
your guide's repository, run `./go create_repo` to remove all of the
pages and images that came with this template (make sure you didn't reuse any
of the file names from this template!) and create a new Git repository:

```
$ ./go create_repo

Clearing Guides Template files.
Removing `:create_repo` command from the `./go` script.
Removing old git repository.
Creating a new git repository.
Initialized empty Git repository in .../MY-NEW-GUIDE/.git/
Creating 18f-pages branch.
Switched to a new branch '18f-pages'
Adding files for initial commit.
All done! Run 'git commit' to create your first commit.
```

Then execute `git commit -m 'Initial commit'` to create your new Guide!
(Unless you're Git savvy and would like to tweak things a bit first.)

## <a name="create-18f-repo"></a>Create a new 18F GitHub repository

Now you're ready to [create a new 18F GitHub
repository](https://github.com/organizations/18F/repositories/new). You'll
want to set the `Public` attribute under the **Team** section and add a
fitting `Description`.

Do _not_ select **Initialize this repository with a README**. Instead, update
the `README.md` file in your own local repository as necessary.

After submitting the form to create a new repository, you will see GitHub's
instructions to create a local repository and push your changes up to it. At
this point, do the following, replacing `MY-NEW-GUIDE` with the name of your
guide's repository:

```
$ git remote add origin git@github.com:18F/MY-NEW-GUIDE.git
$ git push -u origin 18f-pages
```

Note that you can update the description and add a website link to the
repository after creating it:

<img src="{{site.baseurl}}/images/description.png" alt="Setting the
description and website of the GitHub repository">
