# Sessions, Windows and Panes

When you run "tmux", it creates a new tmux session. A tmux session is a container for windows and panes. A window contains 1 or more panes.

# About tmux sessions (outside tmux):

* __tmux__                          # Create a session
* __tmux new -s [name]__  		# Create a session with name
* __tmux a__                       # Attach to the last used session
* __tmux a -t X__                  	# Attach to tmux session with ID or name X
* __tmux ls__                       # Show the current active sessions
* __tmux kill-session -t X__  	# kill tmux session X

# About tmux sessions (in a tmux session):
* __Ctrl-b (__      # previous session
* __Ctrl-b )__      # next session
* __Ctrl-b s__      # choose a session from a list

# About windows :

* Ctrl-b c  	# Create a new window
* Ctrl-b b/n    # Switch between windows
* Ctrl-b X      # Switch to terminal X
* Ctrl-b d      # Detach
* Ctrl-b ,      # Rename the window
* Ctrl-b w     	# Show the list of windows

# About Splits :

* Ctrl-b «  	      # Split the current windows horizontally
* Ctrl-b %            # Split the current windows vertically
* Ctrl-b arrows       # Navigate between splits
* Ctrl-b z            # Toggle full-screen for the current split
* Ctrl-b alt + arrows # Resize the current split

# Others:

* Ctrl-b ?     # Show all commands
* Ctrl-b t     # Show the time in the current split
* Ctrl-b o     # switch between the split
* Ctrl-b space # change the layout of the splits
* Ctrl-b q     # show the numbers of the splits
* Ctrl-b L     # ‘last’ (previously used) session
