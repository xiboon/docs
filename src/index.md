---
label: Welcome
icon: home
---

# Welcome to Runfile

**Runfile** is a command line utility and a Ruby library that helps you create feature-rich command line utilities for your projects.

You create a `Runfile`, and execute commands with `run command arguments -and --flags`.

<object data="/assets/cast.svg" style='width:100%'></object>

[!button variant="info" icon="screen-full" text="Enlarge Demo"](/demo/)

If you are familiar with Ruby's [Rake][rake], or with Makefile, then the concept of Runfile should be familiar to you.

Under the hood, Runfile makes use of the [Docopt][docopt] library, so that you can define your command's argument in an intuitive way.

For example, the below `usage` methods uses a docopt string, to define a command named `greet` with one required argument (`<name>`) and one optional flag (`[--color]`).

```ruby Example
usage  "greet <name> [--color]"
```

## What is Runfile

Runfile is:

1. A command line utility named `run`
2. A Domain Specific Language (DSL) in the form of Ruby methods, to help you define your program's behavior.

A simple Runfile looks like this:

```ruby Runfile
usage  "greet <name>"
help   "Say hello to <name>"
action :greet do |args|
  puts "Hello #{args['<name>']}" 
end
```

And this Runfile can be executed by running:

```shell
$ run
Usage:
  run greet <name>
  run (-h|--help)

$ run greet you
Hello you
```

## Examples

The GitHub repository of Runfile contains many documented examples, showing different aspects of its functionality.

[!button variant="primary" icon="code-review" text="Open Examples"](https://github.com/DannyBen/runfile/tree/master/examples#readme)


## Installation

Runfile comes as a Ruby gem and is primarily designed for Ruby developers.

To install Runfile, run:

```shell
$ gem install runfile
```


[rake]: https://github.com/ruby/rake
[docopt]: http://docopt.org/
