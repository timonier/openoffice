# README

The free and Open Source productivity suite

## Installation

Linux users can use the [installer](https://github.com/timonier/soffice/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/openoffice/raw/master/bin/installer" | sudo sh -s -- install
```

## Usage

### soffice

Run the command `soffice`:

```sh
# Start OpenOffice

soffice
```

### unoconv

Run the command `unoconv`:

```sh
# See all unoconv options

unoconv --help

# Convert docx to html

unoconv --format html --output /path/to/doc.html /path/to/doc.docx
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

If you like / use this project, please let me known by adding a [★](https://help.github.com/articles/about-stars/) on the [GitHub repository](https://github.com/timonier/openoffice).

## Links

* [dagwieers/unoconv](https://github.com/dagwieers/unoconv)
* [image "timonier/openoffice"](https://hub.docker.com/r/timonier/openoffice/)
* [openoffice](https://www.openoffice.org/)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
