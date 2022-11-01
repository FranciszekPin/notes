# Vim advanced usage

## Movement

`[enter]` - first character of next line

`-` - first character of previous line

`z-` - move cursor to the bottom and scroll

`^` - move to first nonblank character of current line

`{`, `}` - prev/next paragraph (empty line)

`;`, `,` - repeat `f` or `t` in same/opposite directions

`nG` - go to line **n**

`%` - move to matching bracket

## Operations

`P` - place text **before** cursor

`cc`, `S` - delte line, start **insert** mode

`J` - join current and next line

`^D`, `^T` - change indentation in *insert mode*

## Starting vim

`vim -c command [file]` - open *file* with running *command*
`vim -R [file]` - open *file* in readonly mode

## Registers

`TODO`

## Marking

`mx` - set mark named *x*

`'x` - go to mark named *x*

## Useful `ex` commands

Find and display all line in the file that don't conatin *pattern*;
also display the line number for each line found

`:g!/pattern/`

## Saving and exiting files

Write to another file

`:w new_file.txt`

## Customization

Show all options set

`:set all`

Show options changed

`:set`

## `Ctags`

Powerful tool. Generate tags

`:!ctags *.c`

Find symbol

`:tab symbol`

Find symbol having cursor on it

`^]`

Go back in tag stack

`^T`

List tag stack

`:tags`

## Multiwindow editing

Open multiple files for split

`vim -O file1 file2 ...`

Split window

`:split`, `:vsplit`

Or, by using key shortcuts:

`^Ws`, `^Wv`
