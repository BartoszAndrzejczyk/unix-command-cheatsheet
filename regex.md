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

- `{2}` maches 2 times
```console
$ echo "froog" | grep -E "fro{2}g"
froog
```
```console
$ echo "frooog" | grep -E "fro{2}g"
```

- `{2,}` matches 2 or more times
```console
$ echo "froog" | grep -E "fro{2,}g"
froog
```
```console
$ echo "frog" | grep -E "fro{2,}g"
```
- `{2,5}` matches from 2 to 5 times
```console
$ echo "froooog" | grep -E "fro{2,5}g"
froooog
```
```console
$ echo "frog" | grep -E "fro{2,5}g"
```
- `or operator` allows matching one of arguments separated by pipe(|)
```console 
$ echo "Ale" | grep -E "A(la|ze|le)"
Ale
$ echo "Ale" | grep -E "A(la|ze)"
```
- `\d` finds string that has number in it (\D is reverse of it).
 Matches a digit (equivalent to [0-9])
```console
$ echo "frog123" | grep -P "\d"
frog123
$ echo "frog123" | grep -P "\D"
```
- `\w` matches any word character (equivalent to [a-zA-Z0-9_])(\W is reverse of it)
 ```console
$ echo "rosfjafjpsa" | grep -P "\w"
rosfjafjpsa
$ echo "$.*" | grep -P "\w"
```
-`\s` matches any whitespace character (\S is reverse of it)
```console
$ echo "f r o g 123" | grep -P "\s"
f r o g 123
$ echo "frog123" | grep -P "\s"
```  
## ancors
- `^` matches the start of a line 
```console
$ echo "super frog" | grep -P "^[a-z]{1,2}"
super frog
$ echo "214super frog" | grep -P "^[a-z]{1,2}"
```
- `$` matches the end of a line
```console
$ echo "super frog" | grep -P "[a-z]{1,2}$"
super frog
$ echo "super frog132" | grep -P "[a-z]{1,2}$"
```
- `^$` matches start and end of a line
```console
$ echo "frog" | grep -P "^[a-z]{1,4}$"
frog
$ echo "froog" | grep -P "^[a-z]{1,4}$"
```