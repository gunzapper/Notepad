Tmux User man
==============

Tmux is a terminal multiplexer, like [GNU screen](www.gnu.org/s/screen/). You can use it with [Byobu](http://byobu.co/).

To store the sessions you could use
[tmuxinator](https://github.com/tmuxinator/tmuxinator)

It is used to work with alternative sessions, one for each work.
It is awesome when you need to do something in background, or when you work in remote connection, like *ssh* . In this way is an alternative to `nohup`.

Install
-------

On Ubuntu use `apt-get install tmux`

After configure `~\.tmux.conf`. This is [Vince Bufalo configuration](https://github.com/gunzapper/bds-files/blob/master/chapter-04-working-with-remote-machines/.tmux.conf). It is very nice, because use `Ctrl+a` to start a *Key Sequence*.


    # Set Tmux's default keystroke to C-a, a binding which comes from GNU Screen
    # and is quite common among Tmux users.
    set-option -g prefix C-a
    unbind C-b

    # fix emacs C-a
    bind a send-prefix

    # Better colors
    set -g default-terminal "screen-256color"

    # Create a cleaner status bar
    set -g status-bg blue
    set -g status-fg white
    set -g status-left '#[fg=green]#S'
    set-window-option -g window-status-current-bg red

    # Creating panes easier.
    unbind %
    bind | split-window -h # split horizontally with C-a |  
    bind - split-window -v # split vertically with C-a -
    
Sub commands
-----------

- List all sessions

     tmux list-sessions 
 
- Create a new session 
    
     tmux new-session -s "session-name"
 
- Kill a session

    tmux kill-session -t "session-name"

- Attach a session 

     tmux attach-session -t "session-name"
 
- Detach a session and attach again 
 
     tmux attach-session -d -t "session-name"
     
Key Sequences
--------------

- List of all keys sequences

     C-a ?

### Window

- Detach

     C-a d
     
- Create new window

     C-a c
     
- Go to next window

     C-a n
     
- Go to previous window

     C-a p
     
- Kill current window

     C-a &
     
- Rename current window

    C-a ,
    
### Pane

- Split horizontally

    C-a | 
    
- Split vertically

    C-a -
    
- Change pane

    C-a 'arrow'
    
- Kill pane

    C-a x 

### Scrolling

- Scrolling on

    C-a Pup

- Scrolling off

`Esc` or `q`
