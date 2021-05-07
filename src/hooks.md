# Event Hooks

The library offers extensive hook capabilities for all stages of a menus' lifecycle. Let's look at the official
`menu_hooks_example.py`. In particular, we will zoom in on the method adding our hooks.

```python
from dpymenus import hooks

...
menu.add_hook(hooks.BEFORE, hooks.UPDATE, self.counter)
menu.add_hook(hooks.AFTER, hooks.CLOSE, self.show_total)
...
```

First, we want to import hooks from the library, so we can access the HookEvent and HookWhen enums.

`add_hook` is available on every menu type, and takes 3 arguments: when to call the hook, on which event, and a 
callback function.

## Hook Enums

### HookWhen

| HookWhen | Description |
| ------ | ------ |
| BEFORE | Executes before the specified event runs. |
| AFTER | Executes after the specified event runs.  |

The HookWhen enums are self-explanatory, they just define whether to run your hook before or after the specified 
event.

### HookEvent

| HookEvent | Description |
| ------ | ------ |
| OPEN | Attaches to the open stage. |
| UPDATE | Attaches to the open stage. |
| CLOSE | Attaches to the open stage.  |
| TIMEOUT | Attaches to a timeout event. |

For most of the events, you can see where the hook would be executed on the previous chapter on lifecycles. Each 
event is explicitly listed where its hook will be executed in the call stack. Timeouts are a special case, however. 
This event is called when with a user-defined timeout expires, resulting in the menu closing out.

*There are currently no hooks for user cancels, failures, and session state changes.*
