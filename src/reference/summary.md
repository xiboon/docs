---
icon: dot
---

# `summary`

[!badge text="Optional"]

Defines a short summary to show when running with `--help`.

+++ runfile
```ruby #2
title  'Developer Tools'
summary 'Commands for managing this folder'

action 'commit' do
  system 'git commit -am "Automatic Commit"'
end
```

+++ output
```shell
$ run --help

$ run -h
Developer Tools

  Commands for managing this folder

Usage:
  run commit
  run (--help | -h)

Options:
  --help, -h
    Show this message
```
+++

When using multiple runfiles with the `import` directive, the `summary` of the
imported runfile is also used in the `Commands` section of the main runfile.

+++ runfile
```ruby #2
title  'Developer Tools'
import 'server'

action 'commit' do
  puts 'git commit -am "Automatic Commit"'
end
```

+++ server.runfile
```ruby #2
title   'Server Commands'
summary 'Server amanagement commands'

action 'start' do
  puts 'Starting server'
end
```

+++ output
```shell Output
$ run --help

Developer Tools

Usage:
  run commit
  run server
  run [COMMAND] (--help | -h)

Commands:
  server
    Server amanagement commands

Options:
  --help, -h
    Show this message
```
+++