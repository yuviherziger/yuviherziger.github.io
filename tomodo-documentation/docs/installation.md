# Installation

`tomodo` can be installed using the following methods:

- [Homebrew](#install-with-homebrew) (macOS)
- [pip](#install-with-pip)
- [From source](#install-from-source)

## Install with Homebrew

You can install tomodo with [Homebrew](https://brew.sh/) by running the following commands:

```shell
brew tap yuvalherziger/homebrew-tomodo
brew install tomodo
```

After installing the tool with `brew`, you can run it the following way:

```shell
tomodo --help
```

### Upgrade Homebrew Package

To upgrade the `tomodo` Homebrew package to the latest version, use the following commands:

```shell
brew update
brew upgrade tomodo
```

## Install with pip

To install the tool with `pip`, run the following command:

```shell
pip install tomodo
```

## Install from Source

If you wish to set up a development environment, you can install tomodo using Python. The recommended way to perform
the Python installation is by using the [Poetry](https://python-poetry.org/) Python package manager.

**Requirements:**

* [Python 3.8](https://www.python.org/downloads/release/python-380/) or higher
* [Poetry](https://python-poetry.org/)

#### Install with Poetry Package Manager for Python

If you have the [Poetry](https://python-poetry.org/) Python package manager installed locally, you can install
the CLI the following way:

```shell
git clone https://github.com/yuvalherziger/tomodo.git
cd tomodo
poetry shell
poetry install
```

After installing the tool with Poetry, you can run it the following way:

```shell
tomodo --help
```

#### Install from source with pip

You can install the dependencies with pip using the following command:

```shell
git clone https://github.com/yuvalherziger/tomodo.git
cd tomodo
pip install .
```

After installing the dependencies with pip, you can validate the installation by invoking the help page:

```shell
python tomodo/cmd.py --help
```
