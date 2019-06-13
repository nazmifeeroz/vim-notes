# Mastering Vim Quickly

> Don't wish Vim was easier, wish you were better!

- Skills take time and effort to master.
- May things aren't fun until you're good at them.
- What's important is that you need to understand a few critically important concepts that provide most of the value.

> "Learning to drive a car takes effort. Is that a reason to keep driving your bicycle? No, you realize you need to invest time to learn a skill. Text editing isn't different. You need to learn new commands and turn them into a habit."

## The Art of Learning

- Pareto principle
  - around 80% of what you've doe today, has been pretty much worthless to your bottom line.
- Mini habits
  - The biggest barrier to forming ne habits is usually the fact that it takes discipline to keep doing something you don't really feel like doing.
- 1% improvement per day

## Opening files

**Method 1** - Open file from terminal

    $ vim /etc/passwd

**Method 2** - Open file from Vim

    $ vim

    :e /etc/passwd

## Jumping around the file

| Command | Description                              |
| ------- | ---------------------------------------- |
| `gg`    | Go to the top of the file                |
| `G`     | Go to the bottom of the file             |
| `{`     | Go to the beginning of current paragraph |
| `}`     | Go to end of current paragraph           |
| `%`     | Go to the matching pair of (), [], {}    |
| `50%`   | Go to line at the 50% of the file        |
| `:NUM`  | Go to line NUM. :28 jumps to line 28     |

## Navigating Inside the window

| Key | Description                                                |
| --- | ---------------------------------------------------------- |
| `H` | Move Cursor to first (**h**ighest) line in current window. |
| `L` | Move Curson to the lowest line of current window.          |
| `M` | Move cursor to the middle of the current window.           |

> ### **Tip**:
>
> While in Insert Mode, you can press **Ctrl-o** to get back to Normal mode and execute one command, after which you'll be automatically returned to Insert mode.
>
> For example: You could press `Ctrl-o F m` to move to previous `m` character and get to Insert mode.

## Searching for the current word

| Key | Description                                           |
| --- | ----------------------------------------------------- |
| `*` | search forwards for the next occurrence of that word. |
| `#` | search backwards for the under your cursor.           |

## Search History

| Key         | Description                                     |
| ----------- | ----------------------------------------------- |
| `/pattern`  | Search a word forward.                          |
| `?pattern`  | Search a word backword.                         |
| `5/pattern` | Search a word and jumps to the fifth occurence. |

- press `/` and hit `Enter` - an empty pattern will repeat last search

| Key      | Description                       |
| -------- | --------------------------------- |
| `Ctrl-o` | Jump back to previous position    |
| `Ctrl-i` | Jump forward to previous position |

## File Manager in Vim

| Command     | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| `:Ex`       | open current directory.                                      |
| `:Ex <dir>` | open specified directory `<dir>`.                            |
| `:Sex`      | open current directory in horizontal split window.           |
| `:Vex`      | open current directory in vertical split window.             |
| `:Tex`      | open current directory in a new tab.                         |
| `:Lex`      | open current directory in vertical split window on the left. |

> **Good Way to Split Window**
>
> `:40vs +Ex`
>
> Opens current directory with width of 40 columns.

> **Changing View types in Explorer**
>
> Hit `i` to cycle through the view type. There are four of them: _thin, long, wide and tree_.

## Changing how files are opened

    $ vim /home/jole

| key       | Description                                              |
| --------- | -------------------------------------------------------- |
| `<Enter>` | Opens the file under the cursor, or enters the directory |
| `D`       | deletes the file under the cursor                        |
| `R`       | renames the file under the cursor                        |
| `X`       | executes the file under the cursor                       |
| `%`       | Creates a new file in the directory                      |

## Undo and Redo

| Command       | Description                                            |
| ------------- | ------------------------------------------------------ |
| `:earlier 2d` | Undo the changes in last two days                      |
| `:ea 3h`      | Undo changes in last three hours                       |
| `:ea 1m`      | Undo changes in last one minute                        |
| `:later 5m`   | Redo all the changes in last 5 minutes                 |
| `:lat 15s`    | Redo all the changes in last 15 seconds                |
| `earlier 3f`  | Undo last three file states (last three buffer writes) |

# Do you speak Vim?

## Vim Language Elements

- Verbs
- Modifiers
- Nouns

### Powerless Verbs

- They can only apply to a single character

| Key | Description                                                 |
| --- | ----------------------------------------------------------- |
| `x` | delete character under the cursor to the right              |
| `X` | delete character under the cursor to the left               |
| `r` | replace character under the cursor with another character   |
| `s` | delete character under the cursor and enter the Insert mode |

### Powerful Verbs

> Note: These commands are usually known as operator commands or operators

| Key | Description                                                  |
| --- | ------------------------------------------------------------ |
| `y` | **y**ank (copy)                                              |
| `c` | **c**hange                                                   |
| `d` | **d**elete                                                   |
| `v` | **v**isually select (not really a verb, but used with verbs) |

### Modifiers

- Modifiers are used right before nouns

| Key   | Description                                                   |
| ----- | ------------------------------------------------------------- |
| `i`   | inner (**i**nside)                                            |
| `a`   | **a**round                                                    |
| `NUM` | number (e.g.: 1, 2, 10)                                       |
| `t`   | searches for something and stops before it (search un**t**il) |
| `/`   | find a string (literal or regular expression)                 |

### Nouns

- In English, nouns can be objects you do something to. It's th same in Vim. Here are the most important ones:

| key      | Description                                               |
| -------- | --------------------------------------------------------- |
| `w`, `W` | start of next **w**ord or **W**ord                        |
| `b`, `B` | start of previous word or WORD (start of word **b**efore) |
| `e`, `E` | **e**nd of word or WORD                                   |
| `s`      | **s**entence                                              |
| `p`      | **p**aragraph                                             |
| `t`      | **t**ag (in context of HTML/XML)                          |
| `b`      | **b**lock (in context of programming)                     |
| `$`      | end of line                                               |
| `^`, `0` | start of line                                             |

- These can be expanded and give you more power:

| key  | Description                |
| ---- | -------------------------- |
| `aw` | **a** (complete) word      |
| `as` | **a** (complete) sentence  |
| `ap` | **a** (complete) paragraph |
| `iw` | **i**nner **w**ord         |
| `is` | **i**nner **s**entence     |
| `ip` | **i**nner **p**aragraph    |

## The "Dot" Command

- Hitting `.` in `Normal` mode will repeat the last native Vim command you've executed
- execute `4.` instead of pressing `....`

# Substitution

## Ranges

| Example             | Description                                                     |
| ------------------- | --------------------------------------------------------------- |
| `:s/bad/good/g`     | changes all words `bad` to `good` in the current line           |
| `:6,11s/bad/good/g` | makes the same change, but in lines 6 to 11, including 6 and 11 |
| `:%s/bad/good/g`    | makes the same change in entire file                            |

## Search and replace

`:[range]/[old value]/[new value]/[flag]`

| flags | Description                           |
| ----- | ------------------------------------- |
| `c`   | to confirm each substitution          |
| `g`   | to replace all occurences in the line |
| `i`   | ingnore case for the pattern          |
| `I`   | don't ignore case for the pattern     |
