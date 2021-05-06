# Lifecycle

Menus consist of three basic stages: open, update, and close. Most of the time is spent in the update stage, which 
processes user input, handles transitions, and manages any state data. In general, you don't really need to know 
anything about menu state management unless you are using hooks *(in the next chapter)* or overriding the `BaseMenu` 
class. 

This page can be used as a reference for the menu lifecycle.

### Open

When a menu is opened, it will always execute these steps first:

1. Attempt to create or acquire (if enabled) a user session
2. Initialize the history and starting page
3. Execute any open hooks
4. Send the initial message (and initializes the `output` attribute)
5. Sets the `input` attribute
6. Updates the history
7. Deletes the input message
8. (Optional) Executes specific menu methods
9. Executes any post-open hooks
10. Executes any pre-update hooks

### Update

An update cycle is performed on every iteration of a menu, whether a page change is executed or not. The steps vary per
menu, but generally look as follows:

1. Wait for user input
2. Assign input to a variable
3. Execute methods based on input checks
4. Execute any post-update hooks
5. Execute transition method (whether it's next, close, or wait)

### Close

When a menu is closed, it goes through the following steps:

1. Execute any pre-close hooks
2. Closes out user session
3. Deletes the Discord message
4. Executes any post-close hooks
