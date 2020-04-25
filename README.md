![Website Build Deployment](https://github.com/swkChemnitz/website-source/workflows/Website%20Build%20Deployment/badge.svg?branch=master)

# Softwerkskammer Chemnitz Website

This repository contains the configuration, content, and theme for the website of the Softwerkskammer Chemnitz.
It does not contain the generated page. That data is pushed to another repository: https://github.com/swkChemnitz/swkChemnitz.github.io

The website is built using [Hugo](https://gohugo.io/).
Check out [Install Hugo](https://gohugo.io/getting-started/installing/) for installation instructions.

## Folder Structure

| Folder                   | Description                                                            |
| ------------------------ | ---------------------------------------------------------------------- |
| [`content/`](./content)  | Source files for the webpage content, i.e., Markdown or Asciidoc files |
| [`static/`](./static)    | Static resources used on pages, e.g., images                           |
| [`themes/`](./themes)    | Submodule(s) for page layout and styles                                |

## Add new Content

In order to add new content to the page, either create a new file in the `content/` directory in the respective subfolder, or use Hugo to prepare the new content:

```shell script
$ hugo new <category>/<filename>
```

This will create a new file with front matter:

```
+++
title =  "Your page title"
date = 2020-04-25T16:27:32+02:00
tags = []
featured_image = ""
description = ""
+++
```

The `title` from the front matter will already show up in the page header.
It is not necessary to repeat it in the content of the file.

The image referenced as `feature_image` is used as background image of the header.

You can add an introduction, short teaser, etc. using the `description` field in the front matter.
The description is displayed under the title in the header.

NOTE: Content does not show up on the page before `date`.

If you want to hide content regardless of the date, you cann add `draft = true` to the front matter.

## Preview the Page

While working on a page, you can use Hugo to serve the web page on your local machine, adding the `-D` flag will also include draft pages:

```shell script
$ hugo serve
```

By default, this command starts a server on localhost:1313.
When content is changed, the page is updated automatically.

## Deployment

The website is made available under https://swkchemnitz.github.io/ via GitHub Pages.
It is served from the `master` branch of the https://github.com/swkChemnitz/swkChemnitz.github.io repository.

Whenever changes are pushed to the master branch, the website is automatically built and pushed via GitHub Actions.
