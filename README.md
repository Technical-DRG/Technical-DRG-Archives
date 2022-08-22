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

sometimes differing Python versions may require you to additionally manually
install search plugins:

```bash
pip install mkdocs-localsearch                                                                                                                                                                                109ms  Mon Aug 22 16:45:56 2022
pip install mdx-spanner
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
