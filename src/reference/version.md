---
icon: dot
---

# `version`

[!badge text="Optional"]

Defines the version string to show when running with `--version`.

+++ runfile
```ruby #2
title   'Developer Tools'
version '1.0.0'

action 'commit' do
  system 'git commit -am "Automatic Commit"'
end
```

+++ output
```shell
$ run --version
1.0.0
```
+++