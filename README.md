# Site DevFest 2020

![](https://github.com/GDGToulouse/site-devfest-2020/workflows/sandbox/badge.svg)

## Requirement

* [Install Hugo](https://gohugo.io/getting-started/installing/)
  Note: you need to install the extended version.

* If you need to use tools, or deploy, you also need [NodeJS](https://nodejs.org/en/).

## Install Theme

```bash
git submodule init
git submodule update themes/devfest-theme-hugo
```

## Commit theme update

When you have made changes on the theme, you need to add the

```
git add themes/devfest-theme-hugo
```

## Run Local site

First run

```bash
npm run build
``` 

Then you can work with Hugo with

```bash
hugo server -D
```

Notice that the `-D` flag is used to render draft elements,
you also can add the `-F` to build elements planed for future.

More information [here](https://gohugo.io/commands/hugo_server/)

## Build

Just run

```bash
hugo
```

More information [here](https://gohugo.io/commands/hugo/)

## Edit data

You can edit

* general information about the site into the `config.toml` file.
* some data into `data/*.yml` files, for header and footer information, team or schedule data.
* some content into `content/**` files.
* some static assets like images into the `static/*` folder

### Create a new blog entry

You can use `hugo new blog/i-create-a-new-entry.md` command and then edit it.
Or just copy an already existing blog entry, and update the content.

### Update the theme

If you need to touch file of the theme (i.e. into `./themes/devfest-theme-hugo/`) you to know one more thing:
 
The theme is in another Git repository <https://github.com/GDGToulouse/devfest-theme-hugo>,
it's using [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules),
so you need to handle this two repository.
 
So this is an example of workflow:
 
* install last NodeJS, see [here](https://github.com/creationix/nvm)
* go into the theme folder `./themes/devfest-theme-hugo/`
* install dependencies with `npm install`
* run `npm start` to launch automatically the build when a file change
* (you still need to launch `hugo server` into the site folder)
* HACK, HACK, HACK
* then build an optimized version with `npm run build`
* then create the PR (or push)
* into the site folder, `git add themes/devfest-theme-hugo`
* then create the PR (or push) 

### Publish

To publish the site on firebase, just run `firebase deploy`.
Note that you need to authenticate once with `firebase login`
YOU DON'T NEED to publish manually the website, it's already done by pushing on `develop` or `master` branches.
 
You could take a look at the `.github/workflows` file

