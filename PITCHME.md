# Tmux 
## (Terminal Multiplexer)

- Source: https://github.com/tmux/tmux
- Mnaual: `man tmux`
- Google Group: https://groups.google.com/forum/#!forum/tmux-users

---

# Why Tmux?

- Mouse free
- Cross Plantform
- Sever/Client
- Just Shell Commands

---

## Pronunciation

- Terminal MUlitipleXer
- Tee Mucks

> The correct pronunciation of "tmux" is a matter of some dispute in my office. Many avoid the issue by installing screen.  @[reddit](https://www.reddit.com/r/linux/comments/yz4r6/screen_vs_tmux/c6034gp/)

---

# Introduction

### Server/Client

- attach
- disconneted

+++

### status-bar

```
Symbol    Meaning
*         Denotes the current window.
-         Marks the last window (previously selected).
#         Window activity is monitored and activity has been
                     detected.
!         Window bells are monitored and a bell has occurred in
                     the window.
~         The window has been silent for the monitor-silence
                     interval.
M         The window contains the marked pane.
Z         The window's active pane is zoomed.
```

+++

### Session:Window.pane

![](session-window-pane.png)

+++

1. Session Management
2. Window Management
3. Pane Management
4. Kill Single Pane

---

# Pair Programming

1. User1 Create a session
2. User2 Join the session(not create a new one)
3. Enjoy!
3. Free to kill your session!

---

# Automation

- tmux command(all start with tmux)
- bootstrap tmux shell

---

# Key Binding

bind [key] [command]

*case sensitive*

+++

### Quick reload

```
bind r source-file ~/.tmux.conf; display-message "Config Reloaded!"
```

+++

### Prefix key

```
unbind C-b
set -g prefix C-a
bind C-a send-prefix 
```

+++

### Split window

```
unbind %
bind | split-window -h -c "#{pane_current_path}"
unbind '"'
bind - split-window -v -c "#{pane_current_path}" 
```

+++

### Vim T-pad key

```
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R
```

---

# Config

- Status Bar
- Window Name
- Bell
- Copy and Paste

---

# Tmate

Share your screen

---

# Plugins

- Plugin Manager: https://github.com/tmux-plugins/tpm

+++

### tmux-sensible

Basic tmux settings everyone can agree on.
https://github.com/tmux-plugins/tmux-sensible

+++
### mem-cpu-load

CPU, RAM, and load monitor for use with tmux
https://github.com/thewtex/tmux-mem-cpu-load

<img src="cpu-mem-load.png" alt="Drawing" style="width: 400px;height: 350px;"/>

---

# Tmux VS GNU Screen

+++

## tmux

### Pros

- Can send keys to other panes, kind of like an IDE
- Easy keybindings -- with the right config, you'll feel at home from Vim or Screen
- Vim-ish and Emacs-ish bindings built-in
- Good layout management, a lot like a tiling window manager
- Unicode seems to Just Work with modern terminals
- Some terminal issues fixed with TERM=tmux

+++
### Cons
- Slow -- unsure why, but keystrokes seem laggy No more issues with slowness
- Multiplexing forces the whole session width and height to the smallest attached terminal
- Has crashed multiple times on Mac OS X, losing the entire session(happened to me)
- Has failed on Linux after upgrade, where I couldn't reconnect to my old session

+++

## GNU Screen

### Pros
- Extremely stable (v1.0 was in 1987)
- Some terminal issues fixed with TERM=screen
- Emacs-ish bindings built in
- Easy to move and control horizontal panes
- When multiplexing, any attached terminal can resize a pane

+++

### Cons
- No vertical splits without patch (except on Ubuntu)
- Pane splits are lost when detaching
- Getting Unicode to work takes a little finesse and determination
- Crazy status line configuration

+++

## Byobu

- A fork of GNU-screen
- http://byobu.co/

---

# Tmux VS iTerm2

- Cross Plantform

---

# Some Tutorials

0. [`man tmux`](http://man7.org/linux/man-pages/man1/tmux.1.html)
1. https://pityonline.gitbooks.io/tmux-productive-mouse-free-development_zh/content/book-content/Chapter5.html
2. My Blog: https://www.kawabangga.com/?s=tmux

---

# ?
