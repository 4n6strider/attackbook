# To Do

## ProxyChains

```bash
nano /etc/proxychains.conf
```

## TMUX

Commands

```text
tmux new -s session_name
tmux attach -t session_name
tmux list-sessions
tmux detach (prefix + d)

tmux split-window (prefix + ")
tmux split-window -h (prefix + %)

tmux source-file ~/.tmux.conf
```

Customization

```text
# remap prefix to Control + a
set -g prefix C-a
unbind C-b
bind C-a send-prefix

# force a reload of the config file
unbind r
bind r source-file ~/.tmux.conf

# quick pane cycling
unbind ^A
bind ^A select-pane -t :.+
```

Logging

```text
tmux pipe-pane -o 'cat >>~/output.#I-#P'
```

















look at [https://jivoi.github.io/2015/08/21/pentest-tips-and-tricks-number-2/](https://jivoi.github.io/2015/08/21/pentest-tips-and-tricks-number-2/)

banner grap with curl -i -L -s 

Review: [https://github.com/xapax/security](https://github.com/xapax/security) and [https://github.com/xapax/security/blob/master/common\_web-services.md](https://github.com/xapax/security/blob/master/common_web-services.md)

Use NMAP results to build diagram:

{% embed url="https://about.draw.io/automatically-create-draw-io-diagrams-from-csv-files/" %}

{% embed url="https://linuxjourney.com/lesson/system-logging" %}





