# Templates

Templates are objects you can apply to a menu which applies a style or attribute across all pages. Some examples include color, footers, and fields.

## Usage

```python
from dpymenus import PaginatedMenu, Template

template = Template(...)
menu = PaginatedMenu(ctx)
menu.add_pages([...], template=template)
```

We want to import the `Template` class, which is exposed in the base dpymenus namespace. We can then create a new Template instance.

The template takes a variety of keyword arguments:

- title: *string*
- description: *string*
- color: *string*
- footer: *dictionary* -> { text: *string*, icon_url: *string* }
- image: *string*
- url: *string*
- thumbnail: *string*
- author: *dictionary* -> { name: string, url: string, icon_url: string }
- fields: *list* -> *dictionary* -> { name: *string*, value: *string*, inline: *boolean* }
- *field_style**
- *field_sort**

    **see the **[next page](./field_overrides.md)** for details*

Most of these are self-explanatory, as they mirror the same attributes on an Embed or Page. An important distinction is what values they take -- typically favoring a single string representing the data.

## Footer, Author, & Fields

The Footer and Author arguments take a dictionary containing the same keys one would normally use when adding these to an Embed or Page.

Fields are a bit different, as you generally create them by calling a separate `.add_field()` function every time. In this case, you pass a list as the argument containing a dictionary for each field. The dictionary, again, contains the same values used when creating them on a standard Embed or Page.
