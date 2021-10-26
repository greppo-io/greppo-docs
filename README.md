# docs.greppo.io

Repository used for building the documentation [docs.greppo.io](https://docs.greppo.io).

Greppo uses Sphinx for building its documentation.

## Development build Setup

```bash
# install dependencies inside a virtual environment
$ pip install -r requirements.txt

# serve with hot reload at 127.0.0.1:8000
$ make live-build

# build static html 
$ make build

# serve static html
$ make serve
```

## Directories and folder structure

### `source`

The directory that contains all the files for building the docs, including the configuration file `conf.py`.

### `build`

The directory that contains the files for built static website. The folder `/html/` contains the static files that need to be served.

### `source/assets`

The assets directory contains all uncompiled assets such as images.

### `source/_static`

This directory contains the static files used for custom styling.

### `source/_template`

This directory contains the html code for custom templating.

## Dependencies

### Sphinx

Sphinx is a tool that makes it easy to create intelligent and beautiful documentation. It was originally created for the Python documentation, and it has excellent facilities for the documentation of software projects in a range of languages.

Plugins used:
*   [sphinx-autobuild](https://github.com/executablebooks/sphinx-autobuild#readme) provides a live-reloading server, that rebuilds the documentation and refreshes any open pages automatically when changes are saved. This enables a much shorter feedback loop which can help boost productivity when writing documentation.
*   [sphinx-copybutton](https://github.com/executablebooks/sphinx-copybutton#readme) project adds a convenient copy button to code blocks. This is a subtle but effective user experience improvement when there are code snippets that a user might wish to copy from (examples, sample code etc).

### Theme: Furo

[Furo](https://pradyunsg.me/furo/) theme is used for styling the documentation. This has to be the cleanest and very well maintained theme for sphinx. Its settings for font, font-sizing and spacing is great out of the box. Has the three column structure of TOC, Page and Page TOC that is well made. It is highly customizable.

### MyST (Markedly Structure text)

[MyST](https://myst-parser.readthedocs.io/en/latest/) is a rich and extensible flavor of Markdown meant for technical documentation and publishing using Sphinx. It provides an interface to write docs in markdown to be rendered in Sphinx. 