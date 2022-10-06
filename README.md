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
frog
```
The pattern was found because second `o` was matched 0 times.
Sample 2
```console
$ echo "froooooooog" | grep "froo*g"
froooooooog
```
The pattern was found because `o` was matched many times.

- `+` - matches 1 or more times
```console
$ echo "frog" | grep "froo+g"
```
Grep does not find second `o` one or more times in the word "frog".
```console
$ echo "frooog" | grep -E "froo+g"
```
grep found one or more `o` in "frooog" 
- `?` matches 0 or 1 time
```console
$ echo "frog" | grep -E "froo?g"
frog
```
The regex expects text frog with 1 or 2 `o`, 1 was given.

```console
$ echo "frooog" | grep -E "froo?g"
```
The regex expects text frog with 1 or 2 `o`, 3 were given.
