---
icon: dot
---

# `shortcut`

[!badge text="Optional"]

Defines a shortcut string that will be expanded before running anything. Note
that this operates on the ARGV level. This is useful for creating short strings
that expand to longer command lines.

+++ runfile
:::code source="../../code/shortcut/runfile" language="ruby":::
+++ output
:::code source="../../code/shortcut/output.txt":::
+++

Since these shortcuts are expanded as if the user has typed the longer command
line, this feature can also be used to access commands in imported files.

+++ runfile
:::code source="../../code/shortcut2/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/shortcut2/server.runfile" language="ruby":::
+++ output
:::code source="../../code/shortcut2/output.txt":::
+++