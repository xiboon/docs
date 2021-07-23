---
icon: book
collapsed: true
order: 90
---

# Reference

**Runfile is ruby**. You can write any ruby code in it as usual.

!!! Tip
To create an initial Runfile, go to a folder that does not contain one already, and execute `run new`.
!!!

Runfile provides several commands to help you define your program and a handful of utility functions to make writing beautiful command line applications a breeze.

A simple Runfile looks like this:

```ruby Runfile
usage  "greet <name>"
help   "Say hello to <name>"
action :greet do |args|
  say "Hello #{args['<name>']}" 
end
```

[!button variant="primary" icon="code-review" text="More Examples"](https://github.com/DannyBen/runfile/tree/master/examples)

## [Defining Program Details](defining-program-details.md)

Commands to specify information about the program, such as its name and version.

## [Defining Program Actions](defining-program-actions.md)

Commands to define program actions

## [Output Commands](output-commands.md)

Commands that can be executed in any action to print colorful, indented messages to the console.

## [Execution Commands](execution-commands.md)

Commands that can be executed in any action to run external programs in the foreground or background easily.

## [Misc Commands](misc-commands.md)

Additional commands you can use in your action blocks.


