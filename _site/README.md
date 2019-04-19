[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# Red Hat UXD Design Tracker Template

This template is for creating a website to track designs created by a UXD team. Built on Jekyll using GitHub pages, this template will enable you to quickly get up and running with a basic set of sortable and filterable tables, patterns for adding designs links and sharing stories from any issue tracking system.

View the [Changelog](CHANGELOG.md)

View the [Wiki](https://github.com/rh-uxd/design-tracker-template/wiki)

### ** Contents: **
- [Installation](#installation)
  - [First Time Build](#first-time-build)
  - [Subsequent Builds](#subsequent-builds)
- [Troubleshooting](#troubleshooting)
- [Site Configuration](#site-configuration)
  - [Navigation](#navigation)
  - [Permalinks](#permalinks)

---

## Installation

| This installation requires that you have Ruby, Node, Gem, Jekyll and Gulp installed. You can find a list of dependecies with versions here: [Design Tracker Dependencies](https://github.com/rh-uxd/design-tracker-template/wiki/Dependencies)

1. Fork this repository
1. Rename as desired (we recommend with UX in the name)
1. Clone to your local machine
1. With Node, Gulp, Ruby, Gem and Jekyll already installed, run `npm run initialize`
1. Start with `jekyll serve`
1. Code away!

### First Time Build
1. Verify that you have the following installed (see our [Dependencies](https://github.com/rh-uxd/design-tracker-template/wiki/Dependencies):
    - Node
    - Gulp
    - Gem
    - Jekyll
2. Run `npm run initialize`
    - commands as part of the script:
      - `gem install bundler`
      - `bundle install`
      - `npm install`
      - `gulp`
        - this will copy the files from your npm_modules directory to their respective locations for the jekyll build process
      - `jekyll build`
    - if this script fails, at the `jekyll build` step, run `bundle exec jekyll build`
3. run `jekyll serve`
    - for viewing locally at http://localhost:4000

### Subsequent Builds
1. `jekyll serve` to start your environment on port `:4000`.

## Troubleshooting
- If you are having issues with the site building, you can run a set of cleaning commands to reset your environment.
- If you have issues with the ***gem bundler***, try to update your bundles with `bundle update`.

#### Environment Troubles
- `npm run reinstall`
    - This will clear out your **node_modules** folder, any vendor folders, reinstall all modules and copy vendor files back to their respective locations.
- `gulp cleanVendors`
    - This will remove just the vendor files that were copied over during the `gulp` process.
    - Run `gulp` to copy a clean set of vendor files back to your directories.

## Site Configuration
The Design Tracker Template utilizes [PatternFly](https://www.patternfly.org) as the basis for the UI, which is built off of Bootstrap (3.x).
  - at this time, there are no plans to move the Design Tracker Template to use Bootstrap 4.x

### Navigation
The navigation is based off of Bootstrap's navbar, and can be found under `_includes/nav.html`. Each link is configured using Jekyll's relative path scaffolding, along with an `if page.navbar_active` check. This check will apply the `.active` class to the navigation element, if the active page name matches the checked variable.

**Example:**

** this will apply the `.active` class to the page if "home" is the page's title.
``` js
{% if page.navbar_active == "home" %} class="active"{% endif %}
```

### Icon &amp; Favicon
- To replace the navbar icon, swap out the existing `icon.png` found under `assets/img/icon.png` with your own image.
- To replace the favicon, swap out the existing `favicon.png` found under `assets/image/favicon.png` with your own image.

### Permalinks
The Design Tracker utilizes Jekyll's built in [Permalink](https://jekyllrb.com/docs/permalinks/) solution in order to define simple and easy-to-use links. Each link is configured in the given pages front matter, with a relative path and permalink override. These, combined with the `navbar_active` name and `layout`callout, give each page their proper information.

```markdown
---
layout: designs
title: Design Table Example 1
navbar_active: example1
relative_path: ../
permalink: designs/example1.html
---
```
