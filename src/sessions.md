# Using Session Restoration Settings

## Work In Progress -- Feature Incomplete

Sessions are, basically, a menu instance. Sessions internally are actually IDs linked to a specific menu instance, but on the developer end you likely don't need to know that.

Sessions allow you to control how many menus a single user can open at once before they start closing themselves.

> **Previous Versions**
>
> If you used dpymenus prior to v2, you would be familiar with menus not
> opening at all when you reached a limit. This will never happen now. There
> was also the method `.allow_multisessions()`, which would let you open up
> multiple menus per user. This is now default functionality, configured via
> settings.

## Keeping Multiple Menus Alive

All menus open concurrently and run alongside eachother. This setting is controlled with the `sessions-per-user` value as an upper limit on menus a single user can have open. By default, 10 menus can be opened at once.

If this value is reached, say 11 menus are opened by a single user without being closed, the earliest menu will close automatically.

In general, you should think about how many menus your users realistically need open at once and adjust accordingly. This is intended to prevent too many menus existing and eating up system resources.

## Managing Session Limits

### Per User

### Per Channel

### Per Guild
