https://github.com/ranger/ranger/wiki/Official-user-guide

Config: `~/config/ranger/rc.conf`

Flags are used in the commands `:open_with` and `:shell`.
    `f`   Fork the process.  (Run in background)
    `c`   Run the current file only, instead of the selection
    `r`   Run application with root privilege (requires sudo)
    `t`   Run application in a new terminal window

There are some additional flags that can currently be used only in the `shell` command:
(for example ":shell -w df")
    `p`   Redirect output to the pager
    `s`   Silent mode.  Output will be discarded.
    `w`   Wait for an Enter-press when the process is done
