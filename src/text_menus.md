# Text-Based Menus

Text-based menus are useful when you need a way to parse user text, or just as a means to limit your requests against the Discord API *(button-based menus have inherent overhead because of this)*.

Let's look at the official `text_menu_example.py`.

## Imports

```python
from dpymenus import Page, TextMenu
from dpymenus.constants import CONFIRM
```

We always want to import the `Page` class, as it is an enhanced form of the `Embed`. In addition, we will import the
type of menu we are creating. We will also make use of some constants provided by the library to make validating input
easier. You'll read more on that later.

## Cog Core

```python
class MyTextMenu(commands.Cog):
    def __init__(self, client):
        self.client = client


def setup(client):
    client.add_cog(MyTextMenu(client))
```

The 'core' of a cog, or a `discord.py` command file, generally looks like this. We inherit from the `commands.Cog`
class, and we always supply a `setup` function, which adds the cog to your bot instance. Inside the core, we will be
able to add our command and relevant menu code.

## Command

```python
@commands.command()
async def text(self, ctx):
    page1 = Page(title='Ping Menu', description='Are you absolutely sure you want to send a ping command?', )
    page1.set_footer(text='Type `yes` if you are sure.\nType `quit` to cancel this menu.')
    page1.on_next(self.confirm)

    page2 = Page(title='Ping Menu', description='Pong!')

    menu = TextMenu(ctx)
    menu.add_pages([page1, page2])
    menu.normalize_responses()
    await menu.open()
```

The first lines, the decorator and definition, define our command. Next, we set up several pages. A Page inherits from
Embed, so you have access to all the regular methods and attributes on Embeds here. We do have additional methods
though, which you would notice as `on_next` in this example.

`on_next` is a method which takes a callable *(function or method)* reference and sets it up internally as a page
callback. We will look at the specific callback, `self.confirm`, in a moment.

You'll notice `page2` does not have an `on_next`. This signifies the end of a menu, or the last page.

## Menu Breakdown

```python
menu = TextMenu(ctx)
```

This is how a menu is initialized. It always takes your command context as an argument, and optionally can take a
template. You will read about templates in a later chapter.

---

```python
menu.add_pages([page1, page2])
```

This is how pages are added to a menu instance. It takes a list of Page or Embed objects. In this case, we assigned our
pages to variables *(page1 and page2)* and put those variables in the list argument.

---

```python
menu.normalize_responses()
```

This is a special method for text-based menus that will normalize user input. It strips unnessecary whitespace and
converts it to lowercase. This makes it easier to process the input for you.

---

```python
await menu.open()
```

This method should be the final thing you call on your menu. It will start the menu up, which means running through the
pre-validation steps, creating a user-menu session, and starting the main menu loop. At this point, your menu will be
intractable in Discord.

## Callback Breakdown

```python
@staticmethod
async def confirm(menu):
    if menu.response_in(CONFIRM):
        await menu.next()
```

This is a normal static method. Note that a menu callback must **always** be async. It takes a menu instance as the
argument, so you can access various menu methods and data.

In this example, we will use a special method on the text-based menu class called `response_in`, which checks if the
user input is in the supplied list of data. `CONFIRM` is a list containing values like 'y' and 'yes', so if the user
types a 'y' in chat, this will return true and proceed to the next line.

`next` is a method available on all menu types which simply proceeds to the next available page.

When the menu updates, it will always check if the current page has a callback. Because our second page did not define
one, an internal method will run that closes our menu and ends the user-menu session.
