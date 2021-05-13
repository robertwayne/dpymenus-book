# Passing Dynamic Data Between Pages

Oftentimes you will need to pass data around a menu that could change. For example, let's say you had a menu allowing a user to answer several questions and then confirm them all on the last page. You *can* just add all of the values onto your menu instance itself if they are static, but if they are dynamic, that often means using `setattr()` and `getattr()`, validation checks, etc.

In addition, if the cog loading in your command has various menus which can be instantiated within it, you may be polluting the class with lots of attributes.

There's not neccesarily a right or wrong way to handle this, but the library provides a minor abstraction over this for ease of use. Benefits include not accessing data which your menu shouldn't have access to and simplicity of working with just a dictionary.

To use this abstraction, just call the `.set_data()` method on a menu instance and pass in a dictionary containing the values you will be using.

From there, you can access that instances data with `menu.data.get(val, [default])` as you would with any other dictionary. Scoped and clean!
