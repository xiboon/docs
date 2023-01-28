---
icon: dot
---

# `summary`

[!badge text="Optional"]

Defines a short summary to show when running with `--help`.

+++ runfile
:::code source="../../code/summary/runfile" language="ruby":::
+++ output
:::code source="../../code/summary/output.txt":::
+++

When using multiple runfiles with the `import` directive, the `summary` of the
imported runfile is also used in the `Commands` section of the main runfile.


+++ runfile
:::code source="../../code/summary2/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/summary2/server.runfile" language="ruby":::
+++ output
:::code source="../../code/summary2/output.txt":::
+++