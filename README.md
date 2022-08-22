# Technical DRG Archives

Static site archive for posts on [/r/technicaldrg](https://www.reddit.com/r/technicaldrg/). Deployed live at [Technical DRG Archives](https://technical-drg.github.io/Technical-DRG-Archives/).

![Github Pages Deployment](https://github.com/Technical-DRG/Technical-DRG-Archives/actions/workflows/ci.yml/badge.svg)

## Producing Content

Create suitable Markdown (augmented by various extensions) files under `docs/`.

For the supported markdown extensions, see [Python Markdown](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/)
and [Python Markdown Extensions](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/).
For the most up-to-date reference of which plugins are enabled, see the `markdown_extensions`
section in `mkdocs.yml`. See also [PyMdown Extensions Documentation](https://facelessuser.github.io/pymdown-extensions/extensions/arithmatex/)
for usage reference.

## Development

This archive uses [`mkdocs-material`][mkdocs-material] as the static site
generator.

Make sure you have Python 3 and corresponding pip installed.

Then, install [`mkdocs-material`][mkdocs-material] via

```bash
pip install mkdocs-material
```

Also install [`mkdocs-git-revision-date-localized-plugin`](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin)
via

```bash
pip install mkdocs-git-revision-date-localized-plugin
```

[mkdocs-material]: https://github.com/squidfunk/mkdocs-material

### mkdocs Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

### Project layout

```
mkdocs.yml    # The configuration file.
docs/
    index.md  # The documentation homepage.
    ...       # Other markdown pages, images and other files.
```
