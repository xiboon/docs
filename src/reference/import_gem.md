---
icon: dot
---

# `import_gem`

[!badge text="Optional"]

Import and blend actions from external runfiles that reside in an external gem.
The provided argument is the in the format of `gemname/filename`.

The below example imports the `docker.runfile` from the root directory of the
[runfile-tasks gem](https://github.com/DannyBen/runfile-tasks).

The additional arguments are passed on to the imported file, as `context`.

+++ runfile
:::code source="../../code/import_gem/runfile" language="ruby":::
+++ output
:::code source="../../code/import_gem/output.txt":::
+++

