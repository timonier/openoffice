# README

The free and Open Source productivity suite

If you like / use this project, please let me known by adding a ★ on the [GitHub repository](https://github.com/timonier/openoffice).

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/openoffice/raw/master/bin/installer" | sudo sh -s -- install
```

__Note__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

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

## Links

* [dagwieers/unoconv](https://github.com/dagwieers/unoconv)
* [image "timonier/openoffice"](https://hub.docker.com/r/timonier/openoffice/)
* [openoffice](https://www.openoffice.org/)
* [timonier/openoffice](https://github.com/timonier/openoffice)
