---
icon: dot
---

# `require_context`

[!badge text="Optional"]

This directive can be used in any imported runfile to require that the importing
runfile needs to provide these context variables. When used with the additional
`default: 'value'` argument, this value will be used in case the importing
runfile did not provide a value.

+++ runfile
:::code source="../../code/require_context/runfile" language="ruby":::
+++ server.runfile
:::code source="../../code/require_context/server.runfile" language="ruby":::
+++ output
:::code source="../../code/require_context/output.txt":::
+++
