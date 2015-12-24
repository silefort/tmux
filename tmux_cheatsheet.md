# Sessions, Windows and Panes

When you run "tmux", it creates a new tmux session. A tmux session is a container for windows and panes. A window contains 1 or more panes.

# About tmux sessions (outside tmux):

* __tmux__                    # Create a session
* __tmux new -s [name]__      # Create a session with name
* __tmux a__                  # Attach to the last used session
* __tmux a -t X__             # Attach to tmux session with ID or name X
* __tmux ls__                 # Show the current active sessions
* __tmux kill-session -t X__  # kill tmux session X

# About tmux sessions (in a tmux session):
* __Ctrl-b (__      # previous session
* __Ctrl-b )__      # next session
* __Ctrl-b s__      # choose a session from a list

# About windows :

* __Ctrl-b c__  	  # Create a new window
* __Ctrl-b b/n__    # Switch between windows
* __Ctrl-b X__      # Switch to terminal X
* __Ctrl-b d__      # Detach
* __Ctrl-b ,__      # Rename the window
* __Ctrl-b w__     	# Show the list of windows

# About Splits :

* __Ctrl-b «__  	        # Split the current windows horizontally
* __Ctrl-b %__            # Split the current windows vertically
* __Ctrl-b arrows__       # Navigate between splits
* __Ctrl-b z__            # Toggle full-screen for the current split
* __Ctrl-b alt + arrows__ # Resize the current split

# Others:

* __Ctrl-b ?__     # Show all commands
* __Ctrl-b t__     # Show the time in the current split
* __Ctrl-b o__     # switch between the split
* __Ctrl-b space__ # change the layout of the splits
* __Ctrl-b q__     # show the numbers of the splits
* __Ctrl-b L__     # ‘last’ (previously used) session
