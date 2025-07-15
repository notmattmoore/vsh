# Vim CLI tools

A collection of vim CLI tools: `vess`, `vman`, and `vsh`.

### `vess` --- less + vim
Pipe output from a command to a vim instance for viewing. Example:
```
ls | vess
```
This is distributed as a script, but can be set as an alias in `.zshrc` instead.
```
alias vess="vim -c 'set number' -"
```

### `vman` --- man + vim
Lookup a manpage and view in vim. Example:
```
vman ls
```
This can also just be defined as a function in your `.zshrc`.
```
function vman() { vim -c "Man $@|only"; }
```

### `vsh` --- shell + vim
Read from standard input, put it in a vim instance, and then execute the
results upon exit. It attempts to load the file `~/.binrc/vsh.aliases` before
execution. Usage:
```
vsh [--no-log] [--last|-l|--history|-h|--execute|-e|<file>]
```
This is surprisingly useful in running transient scripts (use `vsh -e`) and for
file management from the command line (`ls | vsh`, then use `rm`, `mv`, etc to
delete and rename files).
