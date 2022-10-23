# unix command-cheetsheet
### Quantifiers
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
