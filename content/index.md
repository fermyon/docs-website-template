title = "Fermyon documentation template"
template = "main"
date = "2022-05-07T00:22:56Z"
[extra]
url = "https://github.com/fermyon/docs-website-template/blob/main/content/index.md"
---

This repository is a template for the documentation websites of Fermyon projects.
It is intended to serve as the starting point for all new Fermyon documentation
websites, and is a practical adaptation of [the Fermyon style guide](https://design.fermyon.dev/).

Starting from this template, you get a few useful features by default, such as
a responsive website with a sidebar layout, suitable for a documentation website,
and dark and light themes that are toggled manually or by automatically with 
system theme changes.

### Creating a new documentation website

Building a Fermyon documentation website using this template is done by running
the `bart new site` command, or by copying
the contents of this repository in the intended destination (for example, the
`docs/` directory in your project repository), then adding your project documentation
in the `content/` directory:

```bash
$ bart new site --git https://github.com/fermyon/docs-website-template docs
```

Then, add new pages in the content directory:

```bash
$ bart new post --title "My new documentation page" --author "Enrico Fermi" docs/content new.md
```

By default, the files in `content/` are not displayed in the sidebar.
To add them, update the desired section in `templates/content_sidebar.hbs` with
your page title:

```html
<p class="menu-label">
    Your section
</p>
<ul class="menu-list">
    <li><a href="{{site.info.base_url}}/new">My new documentation page</a></li>
</ul>
```

Finally, make sure to update the website title, repository, and description
in the site configuration file and in the main page template.

### Running the website locally

Running the generated websites requires installing [Spin](https://spin.fermyon.dev).

To run the newly built website locally, run the following NPM commands:

```bash
# install the local dependencies
$ npm install
# build the styles
$ npm run styles
# run Spin and watch the local directory for changes
$ npm run spin
```
