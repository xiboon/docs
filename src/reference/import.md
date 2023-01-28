---
icon: dot
---

# `import`

[!badge text="Optional"]

Import and blend actions from external runfiles. The provided argument is a
relative path to the file, without the runfile extension, or a glob pattern to
import multiple files.

+++ runfile
:::code source="../../code/import/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/import/server.runfile" language="ruby":::
+++ output
:::code source="../../code/import/output.txt":::
+++

To import multiple files, use a wildcard.

+++ runfile
:::code source="../../code/import2/runfile" language="ruby":::
+++ tasks/server.runfile
:::code source="../../code/import2/tasks/server.runfile" language="ruby":::
+++ tasks/ssh.runfile
:::code source="../../code/import2/tasks/ssh.runfile" language="ruby":::
+++ output
:::code source="../../code/import2/output.txt":::
+++

The `import` directive accepts additional `key: value` pairs, which will be
forwarded to the imported runfile as the `context` hash.

The imported runfile can optionally use the `require_context` directive to
either set default values to context variables, or require that they will be
provided by the importer.

+++ runfile
:::code source="../../code/require_context/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/require_context/server.runfile" language="ruby":::
+++ output
:::code source="../../code/require_context/output.txt":::
+++
