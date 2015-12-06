# Sessions, Windows and Panes

When you run "tmux", it creates a new tmux session. A tmux session is a container for windows and panes. A window contains 1 or more panes.

# About tmux sessions (outside tmux):

* tmux                          # Create a session
* tmux new -s [name]  		# Create a session with name
* tmux a                        # Attach to the last used session
* tmux a -t X                  	# Attach to tmux session with ID or name X
* tmux ls                       # Show the current active sessions
* tmux kill-session -t X  	# kill tmux session X

# About tmux sessions (in a tmux session):
* Ctrl-b (      # previous session
* Ctrl-b )      # next session
* Ctrl-b s      # choose a session from a list

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
