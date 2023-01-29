---
icon: dot
---

# Syntax Highlighting

Since your runfile files are just ruby, you can set your text editor to show
files with a `runfile` extension, as Ruby. This normally also works for main
files that are named `runfile`.

## Vim

To treat runfile as ruby in vim, add this to your `~/.exrc` or `~/.vimrc` file
(create it if it does not exist):

```bash
au BufRead,BufNewFile runfile,*.runfile set syntax=ruby
```

## GitHub

To instruct GitHub code view screens to apply Ruby syntax highlighting to your
runfiles, add a file named `.gitattributes` to your repository, with this
content:

```
runfile linguist-language=Ruby
*.runfile linguist-language=Ruby
```