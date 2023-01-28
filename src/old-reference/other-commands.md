---
icon: dot
---

# Other Commands

Additional commands you can use in your action blocks.

==- :icon-pin: Quick Reference

```ruby
execute 'other_action'
```
===

### `execute`

=== `execute string`

Call another action. This command accepts a single string argument which should include the command as if you type it in the command prompt (only without the `run` prefix).

```ruby Example
execute "theme watch --all"`
```

[!button variant="primary" icon="code-review" text="Cross Call Example"](https://github.com/DannyBen/runfile/blob/master/examples/i_crosscall/Runfile)


===