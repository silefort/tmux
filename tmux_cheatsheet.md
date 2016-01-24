# Tmux Cheatsheet

## From the command line:

    $ tmux                                                  Create a default session
    $ tmux new -s development -n editor                     Creates a session named “development” and names the first window “editor.”
    $ tmux a                                                Attach to the last used session
    $ tmux a -t development                                 Attaches to a session named “development.”
    $ tmux ls                                               List existing tmux sessions
    $ tmux kill-session -t <sessionName>                    Kill <sessionName>
    $ tmux send-keys -t development ’[keys]’ C-m            Sends the keystrokes to the “development” session’s active window or pane.
    $ tmux send-keys -t development:1.0 ’[keys]’ C-m        Sends the keystrokes to the “development” session’s first window and first pane
    $ tmux select-window -t development:1                   Selects the first window of “development,” making it the active window.
    $ tmux split-window -v -p 10 -t dev                     Splits the current window in the “dev” session vertically, and sets the height to 10%
    $ tmux select-layout -t development main-horizontal     Sets the layout for the “development”session to main-horizontal.
    $ tmux -f app.conf attach                               Loads the app.conf configuration file and attaches to a session created within the app.conf file.

## In a tmux Session:

### About Sessions:

    PREFIX d        Detaches from the session, leaving the session running in the background.
    PREFIX (        Go to the Previous Session
    PREFIX )        Go to the Next Session
    PREFIX s        Display a list of Sessions

### About Windows:

    PREFIX c        Creates a new window from within an existing tmux session. Shortcut for   new-window.
    PREFIX 0…9      Selects windows by number.
    PREFIX w        Displays a selectable list of windows in the current session.
    PREFIX ,        Displays a prompt to rename a window.
    PREFIX &        Closes the current window after prompting for confirmation.
    PREFIX n        Move to next window
    PREFIX p        Move to previous window
    PREFIX 0        Move to first window
    PREFIX 1        Move to second window
    PREFIX f        Find a window by name
    PREFIX @        Cycle through the windows

### About Panes:

    PREFIX |        Divides the current window in half vertically.
    PREFIX -        Divides the current window in half horizontally.
    PREFIX o        Cycles through open panes.
    PREFIX q        Momentarily displays pane numbers in each pane.
    PREFIX x        Closes the current pane after prompting for confirmation.
    PREFIX SPACE    Cycles through the various pane layouts.
    Ctrl h          Go Right
    Ctrl j          Go Down
    Ctrl k          Go Up
    Ctrl l          Go Right
    PREFIX H        Resize Pane 
    PREFIX J        Resize Pane 
    PREFIX K        Resize Pane 
    PREFIX L        Resize Pane 
    PREFIX !        Create a new Window from the current Pane
    PREFIX UP       Maximize a Pane into a new Window
    PREFIX DOWN     Restore the Pane
    PREFIX z        Toggle Full Screen for the current Pane

#### Panes Layouts

* __even-horizontal:__ Stacks all panes horizontally, left to right.
* __even-vertical:__   Stacks all panes vertically, top to bottom.
* __main-horizontal:__ One larger pane on the top and smaller panes underneath.
* __main-vertical:__   One large pane on the left, stacks the rest vertically on the right.
* __tiled:__           Arranges all panes evenly on the screen.

### About Buffers:

    PREFIX Esc      Switch to Copy Mode
    PREFIX p        Paste buffer
    PREFIX =        Lists all paste buffers
    PREFIX C-c      Copy last buffer to clipboard
    PREFIX g        Google last buffer

#### Copy Mode:

    h/j/k/l         VI mode
    CTRL-b          Page Up
    CTRL-f          Page Down
    g               To the Top
    G               To the bottom
    v               Enter Visual Mode
    y               Copy Text
    w               Moves the cursor forward one word at a time.
    b               Moves the cursor backward one word at a time.
    f{char}         Moves to the next occurrence of the specified character.
    F{char}         Moves to the previous occurrence of the specified character.
    g               Jumps to the top of the buffer.
    G               Jumps to the bottom of the buffer.
    ?               Starts a search backward through the buffer.
    /               Starts a search forward through the buffer.

### Others:

    PREFIX :        Enters Command mode.
    PREFIX ?        List predefined tmux keybindings
    PREFIX r        Reload the configuration file
    PREFIX f        Send Ctrl f
    PREFIX P        Toggle Log output to <window_name>.log
    PREFIX t        Show the time in the current split

### Command Mode:

    : new-window -n window "top"    Create a new window and launch top in it. Pretty handy for short-term tasks, the tmux windows will close when escape the process
    : source-file [file]            Loads a configuration file. Use this to reload the existing configuration or bring in additional configuration options later.
    : display-message or display    Displays the given text in the status message.

#### Showing and Saving the Buffer

    : show-buffer                       Display the contents of the paste buffer
    : list-buffers                      Display the buffers
    : choose-buffer                     Select a buffer to paste
    : capture-pane                      Captures the selected pane’s visible contents to a new buffer.
    : save-buffer [filename]            Saves the buffer’s contents to the specified file.

## Status Line Variables

    #H                  Hostname of local host
    #h                  Hostname of local host without the domain name
    #F                  Current window flag
    #I                  Current window index
    #P                  Current pane index
    #S                  Current session name
    #T                  Current window title
    #W                  Current window name
    ##                  A literal #
    #(shell-command)    First line of the shell command’s output
    #[attributes]       Color or attribute change

## Tmuxinator

    $ tmuxinator open [name]                      Opens the configuration file for the project   name in the default text editor. Creates the configuration if it doesn’t exist.
    $ tmuxinator [name]                           Loads the tmux session name. Creates the session if no session currently exists, or attaches to the session.
    $ tmuxinator list                             Lists all current projects.
    $ tmuxinator copy [source] [destination]      Copies a project configuration.
    $ tmuxinator delete [name]                    Deletes the specified project.
    $ tmuxinator implode                          Deletes all current projects.
    $ tmuxinator doctor                           Looks for problems with the tmuxinator and system configuration.
