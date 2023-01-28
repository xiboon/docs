---
icon: dot
---

# `title`

[!badge text="Optional"]

Defines the title of the command line utility.

+++ runfile
```ruby #1
title  'Developer Tools'

action 'commit' do
  system 'git commit -am "Automatic Commit"'
end
```

+++ output
```shell
$ run --help

Developer Tools

Usage:
  run commit
  run (--help | -h)

Options:
  --help, -h
    Show this message
```
+++

When using multiple runfiles with the `import` directive, the `title` of the
imported runfile is also used in the `Commands` section of the main runfile
(unless `summary` is defined, in this case it will be used instead).

+++ runfile
```ruby #2
title  'Developer Tools'
import 'server'

action 'commit' do
  puts 'git commit -am "Automatic Commit"'
end
```

+++ server.runfile
```ruby #1
title 'Server Commands'

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
    Server Commands

Options:
  --help, -h
    Show this message
```
+++