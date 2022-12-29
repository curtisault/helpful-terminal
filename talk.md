[Helpful Terminal Repo](https://github.com/curtisault/helpful-terminal)

# Unix Philosophy

The Unix philosophy emphasizes building simple, compact, clear, modular, and extensible code that can be easily maintained and repurposed by developers other than its creators. 
The Unix philosophy favors composability as opposed to monolithic design.

---

## Fun

cmatrix - Matrix animation

asciiquarium - aquarium animation

toilet - ascii text

```
toilet 'WELCOME' --metal --html > toilet.html
```

youtube-dl - Download existing YouTube videos

ncmpcpp - ncurses music player written in c++

---

## Interesting Macos Specific Commands

```
say "anything you want here"
```

```
security find-generic-password -wa "<name_of_wifi>"

security find-generic-password -ga ATT260
```

```
caffeinate

caffeinate -w <PID>
```

---

## Config And Productivity

Useful configurations and productivity tips for the terminal.


### Starting Out

Killing a running process

`CTRL+c`

Exiting a REPL/Program

`CTRL+d`

Suspending a Process

`CTRL+z`

Re-Enter Suspended Process

`fg`

PATH

`echo $PATH`

secrets

alias

environment variables

piping arguments

dotfiles

man pages

---

# Useful Non-Standard Tools for the terminal

fzf - GitHub - junegunn/fzf: A command-line fuzzy finder 

curl (http requests) - curl 

bat - GitHub - sharkdp/bat: A cat(1) clone with wings. 

ripgrep - GitHub - BurntSushi/ripgrep: ripgrep recursively searches directories for a regex pattern while respecting your gitignore 

fd - GitHub - sharkdp/fd: A simple, fast and user-friendly alternative to 'find' 

alternative ag - GitHub - ggreer/the_silver_searcher: A code-searching tool similar to ack, but faster. 

ranger - visual file manager in the terminal

jq (json querying/formatting) - jq 

ncdu (NCurses Disk Usage) - NCurses Disk Usage

thefuck - The Fuck is a magnificent app that corrects errors in previous console commands.

tmux - Getting Started · tmux/tmux Wiki 

---

## tmux

Default Prefix: `ctlr-b`

New Session

```
tmux new -s <session_name>
```

List Sessions

```
tmux list-sessions
```

Detach from session

```
<prefix> d
```

Enter Session

```
tmux a -t <session_name>
```
