---
icon: dot
---

# `action`

[!badge variant='danger' text="Required"]

Defines the action name, shortcut and the block that will be executed.

The action block will receive a single `args` hash containing all the parsed
arguments and flags.

+++ runfile
:::code source="../../code/action/runfile" language="ruby":::
+++ output
:::code source="../../code/action/output.txt":::
+++

Providing a second argument to the `action` directive, denotes a shortcut.
Note that you also need to define this shortcut in the `usage` directive
(unless the action does not require any arguments, in which case `usage` is
optional).

+++ runfile
:::code source="../../code/action2/runfile" language="ruby":::
+++ output
:::code source="../../code/action2/output.txt":::
+++

A runfile may contain on action without a name. This will be the default action
that is executed when running `run` without arguments (instead of showing
usage).

The action name and shortcut may either be strings or symbols. Whichever you
choose is a matter of personal preference.