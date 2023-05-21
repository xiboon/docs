---
icon: dot
---

# Including Modules

Since your runfile code runs inside an `instance_eval` block, you cannot use
Ruby's `include` directive. Use `extend` instead:

```ruby
extend FileUtils

action :debug do |args|
  puts getwd
end
```
