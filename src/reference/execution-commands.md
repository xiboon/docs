---
icon: dot
order: 70
---

# Execution Commands

Commands that can be executed in any action to run external programs in the foreground or background easily.

==- :icon-pin: Quick Reference

```ruby
# --- Running commands and services

run 'pwd'
run! 'pwd' # and exit
run_bg 'rails server'
run_bg 'rails server', log: 'my.log', pid: 'myserver'
stop_bg 'myserver'

# --- Before / After run hooks

before_run do |command|
  command.gsub /^(rails|rake|cucumber)/, "bin/\\1"
end

after_run do |command|
  puts "Finished #{command}"
end

# --- Configuration

Runfile.setup do |config|
  config.pid_dir = 'tmp/pid'
  config.quiet   = true
end

# or...

Runfile.pid_dir = 'tmp'
```

===

## `run`

=== `run string`

Print and run a command. Wait until it is done and continue. This is executed using `system`. If `Runfile.quiet` is true, it will not echo the command to the console.

```ruby Example
run "rails server -b* -p3000"
```

===

## `run!`

=== `run! string`

Print and run a command, then exit. This is executed using `exec`. If `Runfile.quiet` is true, it will not echo the command to the console.

```ruby Example
run! "rails server -b* -p3000"
puts "this message will never be shown"
```

===

## `run_bg`

=== `run_bg string [, options]`

Run a command in the background, which you can later stop with `stop_bg`. 

Available options are:

- `pid` - provide a string that will be used to name the PID file. This is the string you will later use in `stop_bg`. All PID files will be stored in the working directory, or in `Runfile.pid_dir`.
- `log` - provide a filename that will be used to log the output.

```ruby Examples
run_bg 'some/long-running/process'
run_bg 'some/long-running/process', log: 'my.log', pid: 'daemon'
```

===

## `stop_bg`

=== `stop_bg string`

Stop a command started with 'run_bg'. Provide the name of he pid file you used in 'run_bg'

```ruby Example
stop_bg 'server'
```
===

## `before_run`

=== `before_run { block }`

Intercept each call before executed. Can be used to modify the command, run something before it, or cancel it altogether.

Your block receives the command as argument, and should return a command to run or false to stop execution.

```ruby Examples
# Prefix the command with "bin/" if it is rails, rake or cucumber
before_run do |command|
  cmd.gsub /^(rails|rake|cucumber)/, "bin/\\1"
end

# Abort the command execution based on the value of an environment variable
before_run do |command|
  ENV['PREVENT_EXECUTION'] ? false : command
end
```

===


## `after_run`

=== `after_run { block }`

Intercept each call before it exits. Note this is only useful with `run` and `run_bg` but not with `run!` which exits immediately after execution.


```ruby Example
after_run do |command|
  puts "Finished #{command}"
end
```

===

## Configuration

You can configure several aspects of how these commands behave.

Configuration can be done in one of two ways. Either use the direct syntax: `Runfile.option = value`, or provide a block:

```ruby Example
Runfile.setup do |config|
  config.option = value
end
```
Add the configuration anywhere in your Runfile (either inside an action or outside, at the beginning of the file).

### `pid_dir`

=== `pid_dir = string`

Configure folder for PID files. PID files are stored in the working directory by default.

```ruby Example
Runfile.pid_dir = './tmp/pids'
```

===

### `quiet`

=== `quiet = boolean`

Run without echoing the command.

By default, calls to `run` will show the command before running it. Set `quiet` to true to change that.

```ruby Example
Runfile.quiet = true
```

[!button variant="primary" icon="code-review" text="Execution Commands Example"](https://github.com/DannyBen/runfile/blob/master/examples/r_exec/Runfile)


