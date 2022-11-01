# Regular Expressions

## Basic characters

`.` - matches any *single* character

`*` - matches zero or more of the single character that immediately precedes it 

`^` - when at beginning of a regexpr, matches begining of a line

`$` - when at the end of a regexpr, matches end of a line

`\` - escapes special characters

`[...]` - matches any *one* of the characters enclosed between brackets;
ranges are also possible; example: `[:;A-Za-z()]`;
most of the special characters lose their special meaning, except `\`, `-`, `]`
and `^` if is first

`[^...]` - same, but inverse

`\<`, `\>` - matches respectively beginning and end of the word

`\(`, `\)` - save to buffer, use later with `\n`

## POSIX bracket expressions

`[:alnum:]` - alphanumeric characters

`[:alpha:]` - alphabetic characters

`[:lower:]` - lowercase characters

### Example

`[[:alpha:]!]` - match any alphabetic character and exclamation point

## Extended Regular Expressions

If you want to create OR

`pattern1 \| pattern2`

Match proceding item **one or more** times

`\+`

Match proceding item **zero or one** time

`\=`

Match proceding item **n to m** times
`\{n,m}`

A few as possible matching are also aviable, see `:help regex` for more
information

## Character classes (`but in vim`)

`\p` - printable character

`\P` - printable character excluding digits

`\s` - whitespace character (space or tab)

`\S` - anything that is not space or tab

`\b` - backspace

`\e` - escape

`\r` - carriage return

`\t` - tab

