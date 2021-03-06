# Installation

Installing `dpymenus` is very simple. First, ensure you are running Python 3.8 or higher.

> **Version Support**
>
> As of v2, support for 3.7 was dropped due to various internal preferences.
> I try to work with modern versions of the language, so supporting versions far behind
> would be a hindrance to myself and my enjoyment of programming.

Second, make sure you are in your virtual environment *(if you are not using Poetry)*. This trips up many newcomers to
the language, but it's a critical step.

Last, run this in your command-line:

```shell
pip install dpymenus
```

If you use Poetry:

```shell
poetry add dpymenus
```

## Development Branch

If you are interested in using the development branch, you can run:

```shell
pip install git+https://github.com/robertwayne/dpymenus.git@next
```

```shell
poetry add git+https://github.com/robertwayne/dpymenus.git#next
```

Please note that there are no stability or documentation guarantees for this branch. It is **NOT** recommended using the
development branch unless you know what you are doing.
