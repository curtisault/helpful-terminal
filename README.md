## terminal-depot

Helpful reference manual for useful &amp; productive terminal based tools and workflows.

### Platform Specific

[macos](/macos/README.md)
[linux](/linux/README.md)

### Utilities

See the [standard_tools](standard_tools/README.md) folder for utilities that come out of the box for unix systems.

See the [non_standard_tools](non_standard_tools/README.md) folder for additional software available via a package manager.

### Intelligence Gathering

- [Get IP Address](#get-ip-address)
  - [lynx](#ip-browser)
  - [curl](#ip-curl)
- [Download Website](#dl-website)
  - [lynx](#dl-website-lynx)

### Tips n' Tricks

- [Neovim](#neovim)
  - [Bash Output To New Buffer](#nvim-bash-to-buff)
  - [Register Basics](#nvim-reg-basics)
  - [Readonly Registers](#nvim-readonly-reg)
  - [Expression Register](#nvim-expression-reg)

# Intelligence Gathering

## get-ip-address

### ip-browser

If you have either browser installed.

```bash
lynx ifconfig.me

w3m if config.me
```

### ip-curl

```bash
curl -v --trace-time ifconfig.me

# IF you have xh installed
xh ifconfig.me/ip
```

## dl-website

### dl-website-lynx

```bash
lynx -width=200 -dump "https://catalog.data.gov/dataset" > us-gov-databases.txt
```

# Tips n' Tricks

## neovim

### nvim-bash-to-buff

Unnamed

```
:enew | r !<command>
```

Horizontal

```
:new | r !<command>
```

Vertical

```
:new | r !<command>
```

### nvim-reg-basics

[source](https://www.brianstorti.com/vim-registers/)

  The basic usage

   Every register is accessed using a double quote before its name. For example, we can access the content that is in the register r with "r.

   You could add the selected text to the register `r` by doing `"ry`. You are copying (yanking) the selected text, and then adding it to the register `"r`. To paste the content of this register, the
   logic is the same: `"rp`. You are pasting the data that is in this register.

   You can also access the registers in insert/command mode with `Ctrl-r` + register name, like in `Ctrl-r r`. It will just paste the text in your current buffer. You can use the `:reg` command to see
   all the registers and their content, or filter just the ones that you are interested with `:reg a b c`.

```
:reg a b c
--- Registers ---
"a   register a content
"b   register b content
"c   register c content
```

**The unnamed register**

   vim has a unnamed (or default) register that can be accessed with `""`. Any text that you delete (with `d`, `c`, `s` or `x`) or yank (with `y`) will be placed there, and that's what vim uses to paste,
   when no explicit register is given. A simple `p` is the same thing as doing `""p`.

   > Never lose a yanked text again

   It has happened to all of us. We yank some text, than delete some other, and when we try to paste the yanked text, it's not there anymore, vim replaced it with the text that you deleted, then
   you need to go there and yanked that text again.
   Well, as I said, vim will always replace the unnamed register, but of course we didn't lose the yanked text, vim would not have survived that long if it was that dumb, right?

   vim automatically populates what is called the numbered registers for us. As expected, these are registers from `"0` to `"9`.
   `"0` will always have the content of the latest yank, and the others will have last 9 deleted text, being "1 the newest, and "9 the oldest. So if you yanked some text, you can always refer to
   it using `"0p`.

### nvim-readonly-reg

[source](https://www.brianstorti.com/vim-registers/)

**The read only registers**

  There are 4 read only registers: `".`, `"%`, `":` and `"#`
  The last inserted text is stored on `".`, and it's quite handy if you need to write the same text twice, in different places, not needing to yank and paste.

  `"%` has the current file path, starting from the directory where vim was first opened. What I usually use it for is to copy the current file to the clipboard, so I can use it externally
  (running a script in another terminal, for instance). You could execute :let @+=@% to do that. let is used to write to a register, and "+ is the clipboard register, so we are copying the
  current file path to the clipboard.

  `":` is the most recently executed command. If you save the current buffer with `:w`, "w" will be in this register. A good way to use it is with @:, to execute this command again. For example, if
  you execute a substitute command in one line, like in `:s/foo/bar`, you can just to go another line and execute `@:` to run this substitution again.

  `"#` is the name of the alternate file, that you can think of it as the last edited file (it's a bit more complex than that, go to `:h alternate-file` if you want to understand it better). It's
  what vim uses to switch between files when you use `Ctrl-^`, and you could do the same thing with `:e Ctrl-r #`. I rarely use this, but hopefully you are more creative than I am.

### nvim-expression-reg

[source](https://www.brianstorti.com/vim-registers/)

**The expression and the search registers**

  The expression register (`"=`) is used to deal with results of expressions. This is easier to understand with an example. If, in insert mode, you type `Ctrl-r =`, you will see a "=" sign in the command line. Then if you type `2+2
  <enter>`, 4 will be printed. This can be used to execute all sort of expressions, even calling external commands. To give another example, if you type `Ctrl-r =` and then, in the command line, `system('ls') <enter>`, the output of the
  ls command will be pasted in your buffer.

  The search register, as you may have imagined, is where the latest text that you searched with /, ?, * or # is. If, for example, you just searched for /Nietzsche, and now you want to replace it with something else, there is no way
  you are going to type "Nietzsche" again, just do `:%s/<Ctrl-r />/mustache/g` and you are good to go.
