# Tmux



#### Commands <a id="leanpub-auto-commands"></a>

**Session**

| Command | Action |
| :--- | :--- |
| no command | Short-cut for `new-session` |
| `attach-session` | Attach or switch to a session |
| `choose-session` | Put a window into session choice mode |
| `has-session` | Check and report if a session exists on the server |
| `kill-session` | Destroy a given session |
| `list-sessions` | List sessions managed by server |
| `lock-session` | Lock all clients attached to a session |
| `new-session` | Create a new session |
| `rename-session` | Rename a session |

**Window**

| Command | Action |
| :--- | :--- |
| `choose-window` | Put a window into window choice |
| `find-window` | Search for a pattern in windows |
| `kill-window` | Destroy a given window |
| `last-window` | Select the previously selected |
| `link-window` | Link a window to another |
| `list-windows` | List windows of a session |
| `move-window` | Move a window to another |
| `new-window` | Create a new window |
| `next-window` | Move to the next window in a sesssion |
| `previous-window` | Move to the previous window in session |
| `rename-window` | Rename a window |
| `respawn-window` | Reuse a window in which a command has exited |
| `rotate-window` | Rotate positions of panes in a window |
| `select-window` | Select a window |
| `set-window-option` | Set a window option |
| `show-window-options` | Show window options |
| `split-window` | Splits a pane into two |
| `swap-window` | Swap two windows |
| `unlink-window` | Unlink a window |

**Pane**

| Command | Action |
| :--- | :--- |
| `break-pane` | Break a pane from an existing into a new window |
| `capture-pane` | Capture the contents of a pane to a buffer |
| `display-panes` | Display an indicator for each visible pane |
| `join-pane` | Split a pane and move an existing one into the new space |
| `kill-pane` | Destroy a given pane |
| `last-pane` | Select the previously selected pane |
| `list-panes` | List panes of a window |
| `move-pane` | Move a pane into a new space |
| `pipe-pane` | Pipe output from a pane to a shell command |
| `resize-pane` | Resize a pane |
| `respawn-pane` | Reuse a pane in which a command has exited |
| `select-pane` | Make a pane the active one in the window |
| `swap-pane` | Swap two panes |

#### Keybindings <a id="leanpub-auto-keybindings-1"></a>

| Shortcut | Action |
| :--- | :--- |
| `C-b` | Send the prefix key \(C-b\) through to the |
|  | application. |

**Miscellaneous**

| Shortcut | Action |
| :--- | :--- |
| `C-z` | Suspend the tmux client. |
| `r` | Force redraw of the attached client. |
| `t` | Show the time. |
| `~` | Show previous messages from tmux, if any. |
| `f` | Prompt to search for text in open windows. |
| `d` | Detach the current client. |
| `D` | Choose a client to detach. |
| `?` | List all key bindings. |
| `:` | Enter the tmux command prompt. |

**Copy/Paste**

| Shortcut | Action |
| :--- | :--- |
| `#` | List all paste buffers. |
| `[` | Enter copy mode to copy text or view the history. |
| `]` | Paste the most recently copied buffer of text. |
| `Page Up` | Enter copy mode and scroll one page up. |
| `=` | Choose which buffer to paste interactively from a |
|  | list. |
| `-` | Delete the most recently copied buffer of text. |

**Session**

| Shortcut | Action |
| :--- | :--- |
| `$` | Rename the current session. |

**Session Traversal**

| Shortcut | Action |
| :--- | :--- |
| `L` | Switch the attached client back to the last |
|  | session. |
| `s` | Select a new session for the attached client |
|  | interactively. |

**Window**

| Shortcut | Action |
| :--- | :--- |
| `c` | Create a new window. |
| `&` | Kill the current window. |
| `i` | Display some information about the current window. |
| `,` | Rename the current window. |

**Window Traversal**

| Shortcut | Action |
| :--- | :--- |
| `0 to 9` | Select windows 0 to 9. |
| `w` | Choose the current window interactively. |
| `M-n` | Move to the next window with a bell or activity |
|  | marker. |
| `M-p` | Move to the previous window with a bell or activity |
|  | marker. |
| `p` | Change to the previous window. |
| `n` | Change to the next window. |
| `l` | Move to the previously selected window. |
| `'` | Prompt for a window index to select. |

**Window Moving**

| Shortcut | Action |
| :--- | :--- |
| `.` | Prompt for an index to move the current window |

**Pane**

| Shortcut | Action |
| :--- | :--- |
| `x` | Kill the current pane. |
| `q` | Briefly display pane indexes. |
| `%` | Split the current pane into two, left and right. |
| `"` | Split the current pane into two, top and bottom. |

**Pane Traversal**

| Shortcut | Action |
| :--- | :--- |
| `;` | Move to the previously active pane. |
| `Up, Down` | Change to the pane above, below, to the left, or to |
| `Left, Right` | the right of the current pane. |
| `o` | Select the next pane in the current window. |

**Pane Moving**

| Shortcut | Action |
| :--- | :--- |
| `C-o` | Rotate the panes in the current window forwards. |
| `M-o` | Rotate the panes in the current window backwards. |
| `{` | Swap the current pane with the previous pane. |
| `}` | Swap the current pane with the next pane. |
| `!` | Break the current pane out of the window. |

**Pane Resizing**

| Shortcut | Action |
| :--- | :--- |
| `M-1 to M-5` | Arrange panes in one of the five preset layouts: |
|  | even-horizontal, even-vertical, main-horizontal, |
|  | main-vertical, or tiled. |
| `C-Up, C-Down` | Resize the current pane in steps of one cell. |
| `C-Left, C-Right` |  |
| `M-Up, M-Down` | Resize the current pane in steps of five cells. |
| `M-Left, M-Right` |  |

#### Formats <a id="appendix-formats"></a>

**Copy / paste**

| Variable name | Description |
| :--- | :--- |
| buffer\_name | Name of buffer |
| buffer\_sample | Sample of start of buffer |
| buffer\_size | Size of the specified buffer in bytes |

**Clients**

| Variable name | Description |
| :--- | :--- |
| client\_activity | Integer time client last had activity |
| client\_created | Integer time client created |
| client\_control\_mode | 1 if client is in control mode |
| client\_height | Height of client |
| client\_key\_table | Current key table |
| client\_last\_session | Name of the client’s last session |
| client\_pid | PID of client process |
| client\_prefix | 1 if prefix key has been pressed |
| client\_readonly | 1 if client is readonly |
| client\_session | Name of the client’s session |
| client\_termname | Terminal name of client |
| client\_tty | Pseudo terminal of client |
| client\_utf8 | 1 if client supports utf8 |
| client\_width | Width of client |
| line | Line number in the list |

**Panes**

| Variable name | Description |
| :--- | :--- |
| alternate\_on | If pane is in alternate screen |
| alternate\_saved\_x | Saved cursor X in alternate screen |
| alternate\_saved\_y | Saved cursor Y in alternate screen |
| cursor\_flag | Pane cursor flag |
| cursor\_x | Cursor X position in pane |
| cursor\_y | Cursor Y position in pane |
| insert\_flag | Pane insert flag |
| keypad\_cursor\_flag | Pane keypad cursor flag |
| keypad\_flag | Pane keypad flag |
| mouse\_any\_flag | Pane mouse any flag |
| mouse\_button\_flag | Pane mouse button flag |
| mouse\_standard\_flag | Pane mouse standard flag |
| pane\_active | 1 if active pane |
| pane\_bottom | Bottom of pane |
| pane\_current\_command | Current command if available |
| pane\_current\_path | Current path if available |
| pane\_dead | 1 if pane is dead |
| pane\_dead\_status | Exit status of process in dead pane |
| pane\_height | Height of pane |
| pane\_id | Unique pane ID \(Alias: \#D\) |
| pane\_in\_mode | If pane is in a mode |
| pane\_input\_off | If input to pane is disabled |
| pane\_index | Index of pane \(Alias: \#P\) |
| pane\_left | Left of pane |
| pane\_pid | PID of first process in pane |
| pane\_right | Right of pane |
| pane\_start\_command | Command pane started with |
| pane\_synchronized | If pane is synchronized |
| pane\_tabs | Pane tab positions |
| pane\_title | Title of pane \(Alias: \#T\) |
| pane\_top | Top of pane |
| pane\_tty | Pseudo terminal of pane |
| pane\_width | Width of pane |
| scroll\_region\_lower | Bottom of scroll region in pane |
| scroll\_region\_upper | Top of scroll region in pane |
| scroll\_position | Scroll position in copy mode |
| wrap\_flag | Pane wrap flag |

**Sessions**

| Variable name | Description |
| :--- | :--- |
| session\_alerts | List of window indexes with alerts |
| session\_attached | Number of clients session is attached to |
| session\_activity | Integer time of session last activity |
| session\_created | Integer time session created |
| session\_last\_attached | Integer time session last attached |
| session\_group | Number of session group |
| session\_grouped | 1 if session in a group |
| session\_height | Height of session |
| session\_id | Unique session ID |
| session\_many\_attached | 1 if multiple clients attached |
| session\_name | Name of session \(Alias: \#S\) |
| session\_width | Width of session |
| session\_windows | Number of windows in session |

**Windows**

| Variable name | Description |
| :--- | :--- |
| history\_bytes | Number of bytes in window history |
| history\_limit | Maximum window history lines |
| history\_size | Size of history in bytes |
| window\_activity | Integer time of window last activity |
| window\_activity\_flag | 1 if window has activity |
| window\_active | 1 if window active |
| window\_bell\_flag | 1 if window has bell |
| window\_find\_matches | Matched data from the find-window |
| window\_flags | Window flags \(Alias: \#F\) |
| window\_height | Height of window |
| window\_id | Unique window ID |
| window\_index | Index of window \(Alias: \#I\) |
| window\_last\_flag | 1 if window is the last used |
| window\_layout | Window layout description, ignoring zoomed |
|  | window panes |
| window\_linked | 1 if window is linked across sessions |
| window\_name | Name of window \(Alias: \#W\) |
| window\_panes | Number of panes in window |
| window\_silence\_flag | 1 if window has silence alert |
| window\_visible\_layout | Window layout description, respecting |
|  | zoomed window panes |
| window\_width | Width of window |
| window\_zoomed\_flag | 1 if window is zoomed |

**Servers**

| Variable name | Description |
| :--- | :--- |
| host | Hostname of local host \(alias: \#H\) |
| host\_short | Hostname of local host \(no domain name\) |
|  | \(alias: \#h\) |
| socket\_path | Server socket path |
| start\_time | Server start time |
| pid | Server PID |

