---
icon: dot
---

# `title`

[!badge text="Optional"]

Defines the title of the command line utility.

+++ runfile
:::code source="../../code/title/runfile" language="ruby":::
+++ output
:::code source="../../code/title/output.txt":::
+++

When using multiple runfiles with the `import` directive, the `title` of the
imported runfile is also used in the `Commands` section of the main runfile
(unless `summary` is defined, in this case it will be used instead).

+++ runfile
:::code source="../../code/title2/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/title2/server.runfile" language="ruby":::
+++ output
:::code source="../../code/title2/output.txt":::
+++

