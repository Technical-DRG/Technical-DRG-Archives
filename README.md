# Technical DRG Archives

Static site archive for posts on /r/technicaldrg.

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
