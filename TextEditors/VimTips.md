# Tips

Add the following line to your `~/.vimrc` to access `man` in Vim. For example `:Man mpv`

```
runtime ftplugin/man.vim
```
# Moving around

## e and E

* `e` move to the end of a word
* `E` move to the end of a word (any non-whitespace characters)

Suppose the cursor is at the beginning of `std::cout <<`. `e` stops at `d` and `E` stops at `t`.

## w and W

* `w` move forward to the beginning of a word
* `W` move forward a word (any non-whitespace characters)

Suppose the cursor is at the beginning of `std::cout <<`. `w` stops at `:` and `W` stops at `<`.

## b and B

* `b` move backward to the beginning of a word
* `B` move backward to the beginning of a word (any non-whitespace characters)

## 0 and ^ and $

* `0` Move to the beginning o a line
* `^` Move to the first non-blank character of the line
* `$` Move to the end of the line

## H and M and L
* `H` jump to the top of screen
* `M` jump to the middle of screen 
* `L` jump to the bottom of screen



# Book Review

## Group 1:
```
i, I
a, A
s, S
```        
## Group 2:
```
r, R
c, C, cc
d, dd, D
```
---

* `f[char], F[char], t[char], T[char]` page 1
* `2f, 20k`
* `CTRL-G` p19
* `CTRL-D, CTRL-U` p20
* `d3$, 3dd`
* `3d2w p21`
* `cc C` p22
* `D`
* p22 (The `.` command repeats the last change. A change, in this context, is inserting, deleting or replacing text)  

 ## Deleting an HTML tag  

You position the cursor on the first `<` and delete the `<B>` with the command `df>`.

---
* `J` p23
* `r` and `s`
* `5r*` p23
* `5r<ENTER>` p23
* `~, 2~` p24
## p24 Keyboard Macros
`qa <some actions> q`. For using macro three times: `3@a`.
* [Repeat macro recursively](http://vim.wikia.com/wiki/Record_a_recursive_macro):
```
qqq
qq
Commands you want to record
@q
q
@q
```     
* *digraphs:* for example type `CTRL-kCo` for copyright sign
* In search patterns, `"foobeep\&...beep"` matches `foobeep`. `foobeep\&..."` matches `"foo"` in `"foobeep`. see :h pattern
* `:set hlsearch`. `:nohlsearch`. :set `incsearch` p29
* `/` and `?` and `n` and `N` and `/<ENTER>` and `?<ENTER>`
* `/^$ p33`
* `/. p33`
24. **IMPORTANT** see `:h magic`. if you use `"/\V<pattern>"`, you only need to escape `'/'` and `'\'` character with `\` (e.g. `/\V\/` and `/\V\\`) in `<pattern>`; but if you use `"?\V<pattern>"` you only need to escape `'\'` with `'\'` (e.g. `?\V\\`) in `<pattern>`
* `:g/^#/d` Delete all lines that begin with `'#'` character. For more information see this [page](http://vim.wikia.com/wiki/Delete_all_lines_containing_a_pattern)
* `:for i in range(1, 12) | put = printf('%d.', i) | endfor`


# Programming Tips (visit this [site](http://www.moolenaar.net/habits.html))

* Use `%` to jump from an open brace to its matching closing brace. Or from a `"#if"` to the matching `"#endif"`. Actually, `%` can jump to many different matching items. It is very useful to check `if ()` and `{}` constructs are balanced properly.
* Use `[{` to jump back to the `"{"` at the start of the current code block.
* Use `gd` to jump from the use of a variable to its local declaration.
* Vim has a completion mechanism that makes this a whole lot easier. It looks up words in the file you are editing, and also in #include'd files. You can type `"XpmCr"`, then hit `CTRL-N` and Vim will expand it to
* ":abbr Lunix Linux" The words will be automatically corrected just after you typed them.
# Tips

* If you are using [Ack](https://github.com/mileszs/ack.vim) plugin, you can use the following command:

```
:Ack -w -i --ignore-dir=build -w  \"gui\"
```
`-w` means search for the whole word, `-i` means ignore case sensitivity.
