# Constant Variables

The library comes with several pre-defined variables in the constants import to make working with menus a bit more seamless. While I try to provide sane defaults,
each of the options can be overriden.

As you saw on the [previous page](./global_configuration.md), they are simply lists of strings.

## Text Constants

```python
from dpymenus.constants import CONFIRM, DENY, QUIT
```

When creating text-based menus that require users to enter responses, you'll often
need to check for values such as 'yes', 'no', and 'quit'. By default, text-based menus all use the QUIT constants internally to allow users to close out of menus.

## Button Constants

```python
from dpymenus.constants import GENERIC_BUTTONS
```

In general, you shouldn't have to import these directly and they should be overriden using the `pyproject.toml` file. This is used internally for the
PaginatedMenu to display its reaction buttons.

When overriding this value, make sure you place your buttons in the order they
will be displayed on the PaginatedMenu:

    first_page, back, close, next, last_page

Also, note that PagiantedMenu provides a general method for managing this: `add_buttons([...])`. You should prefer to use this method unless you have multiple menus which should have their default buttons overridden.
