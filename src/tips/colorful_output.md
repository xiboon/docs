---
icon: dot
---

# Colorful Output

If you have skimmed through the reference, you may have noticed that the command
`say` is sometimes used instead of Ruby's `puts`. This is provided by the
[Colsole](https://github.com/DannyBen/colsole) gem, which is bundled with
Runfile, and available inside your actions.

In addition, Runfile itself, prints most of its output using `say`, which means
you can use Colsole's color markers in some other places

Colsole's primary function is to provide a way to easily print colorful strings.

```ruby
say 'r`This will be in green`'
say 'nb`This will be in normal bold`'
say 'rubi`This will be in red, underlined, bold, inverted`'
```