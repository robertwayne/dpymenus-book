# Creating Pages

Pages are integral to creating menus. A page is really just an Embed with extra properties, such as various callback functionality. Any valid Embed is a valid Page, but not the other way around.

## Callbacks

When you are using pages in menus other than a PaginatedMenu, you must define callbacks on each page so the menu knows how to generate and what to do when user input is processed. EVERY page other than your last, has to include an `on_next()` callback. The others are optional.

A callback in our case is a reference to a function that you define, which is passed into the `.on_next()` method. It is important that you only pass a reference in, which means exclude the parenthesis.

If you added the parenthesis, it would call the function immediately instead of deferring it for later when the menu executes its next functions.

See the **[API Docs](https://dpymenus.readthedocs.io/en/latest/)** for specific callback functions available on each page.

## Sending Page Instances

If you are using pages in complex or non-standard ways, you should always call the `.as_safe_embed()` method on the instance before sending it via a Discord message.
