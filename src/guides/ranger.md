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

# My config
```
setlocal path=~/Downloads sort mtime


# ALIASES
alias tmux_neww_here eval os.system('tmux neww -c '+ str(fm.fm.thisdir)) if os.getenv('TMUX') else 0
#alias tmux_split_here eval os.system('tmux split-window -v -p66 -c ' + str(fm.fm.thisdir)) if os.getenv('TMUX') else 0
alias tmux_split_here eval os.system('tmux split-window -v -p66') if os.getenv('TMUX') else 0
alias tmux_python3 console shell tmux split-window -v -p66 python3 %f%space

alias make shell -w make
alias vim shell nvim
alias zed shell zed .

# MAPS
## Move bookmarks from m to b
unmap m<any> m<bg> um<any> um<bg>
map b<any>  set_bookmark %any
map ub<any> unset_bookmark %any
map b<bg>   draw_bookmarks
copymap b<bg>  ub<bg> `<bg> '<bg>


## Swap default maps gl <-> gL
map gl cd -r %f
map gL cd -r .

## Custom commands
### Tmux
map ms tmux_split_here
map mc tmux_neww_here
map mp tmux_python3
map ml chain tmux_neww_here; shell tmux splitw -h nvim %f; shell tmux renamew %d

map mk console mkcd%space
map me<any> echo %any_path

map m. source /home/aeek/.config/ranger/rc.conf

map uz console -p15 shell unzip -d  "%f"
map s console shell -w%space
map yi shell cat %f | xclip -selection clipboard -target image/png -i
map zed zed
map zip console -p10 shell zip  %%s
```
