---
icon: dot
---

# `usage`

[!badge variant='danger' text="Sometimes Required"]

Defines a usage string for a given `action`. When the action does not require
any arguments, this is optional.

+++ runfile
:::code source="../../code/usage.runfile" line="2" language="ruby" :::

<!-- ```ruby #3
title  'Developer Tools'

usage  '[NOTE --production]'
option '--production', 'Deploy to production instead of stage'
action 'deploy' do |args|
  note = args['NOTE'] 

  if args['--production']
    puts "Deploying to production (#{note})"
  else
    puts "Deploying to stage (#{note})"
  end
end
``` -->

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