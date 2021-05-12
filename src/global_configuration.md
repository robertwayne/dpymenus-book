# Using pyproject.toml to Configure Menus

General global settings within the library can be configured with a `pyproject.toml` file in your root directory.

Everything should be listed under a `[dpymenus]` header.

### General

| Variable | Type | Default | Description |
| -------- | ----------- | ---------- | ------- |
| history-cache-limit | int | 10 | Limit on the history cache. 0 disables. |
| hide-warnings | bool | False | Shows/hides library warnings in the console. |
| reply-as-default | bool | False | Enables/disables the Discord reply feature. |
| button-delay | float | 0.35 | Delay, in milliseconds, between adding buttons to a page. |
| timeout | int | 120 | Duration, in seconds, before a menu is timed out and closed. |

### Sessions

| Variable | Type | Default | Description |
| -------- | ----------- | ---------- | ------- |
| allow-session-restore | bool | False | Enables/disabled the session restore feature. |
| sessions-per-channel | int | 1 | Limits sessions per channel. |
| sessions-per-guild | int | 3 | Limits sessions per guild. |
| sessions-per-user | int | 10 | Limits sessions per user. |
| session-timeout | int | 3600 | Duration, in seconds, before sessions are removed from the store. |

### Constants

| Variable | Type | Default |
| -------- | ----------- | ---------- |
| constants-confirm | List[str] | ['y', 'yes', 'ok', 'k', 'kk', 'ready', 'rdy', 'r', 'confirm', 'okay'] |
| constants-deny | List[str] | ['n', 'no', 'deny', 'negative', 'back', 'return'] |
| constants-quit' | List[str] | ['e', 'exit', 'q', 'quit', 'stop', 'x', 'cancel', 'c'] |
| constants-buttons | List[str] | ['⏮️', '◀️', '⏹️', '▶️', '⏭️'] |

*See the [next page](./constants.md) for detailed information on constants.*

### Example File

```toml
[dpymenus]
history-cache-limit = 10
sessions-per-channel = 1
sessions-per-guild = 3
sessions-per-user = 10
session-timeout = 3600
allow-session-restore = false
hide-warnings = false
reply-as-default = false
button-delay = 0.35
timeout = 15
constants-confirm = ['yes', 'y']
constants-deny = ['no', 'n']
constants-quit = ['quit', 'q']
constants-buttons = ['⏮️', '⬅️️', '🛑', '➡️️', '⏭️'] 
```

```
[dpymenus]
```
