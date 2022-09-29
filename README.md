# unix-command-cheatsheet

## git

### commit

`git commit` saves changes

Example:
```console
$ git commit -m "Enter here a message"
```
## Terminal navigation
- `ctrl+a` - moves cursor to the begginig of a line
- `ctrl+e` - moves cursor to the end of a line
- `ctrl+k` - deletes text from the position cursor to the end of a line
- `ctrl+y` - yanks perviously deleted text
- `ctrl+<` - moves the cursor to the beggining of a word
- `ctrl+>` - moves cursor to the end of a word
- `ctlr+w` - deletes a word before the cursor
- `esc+d` - delets a word after the cursor
## Quantifiers
- `*` - matches 0 or more times

Sample 1
```console
$ echo "frog" | grep "froo*g"
```
outputs:
