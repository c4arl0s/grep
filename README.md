# grep

File pattern searcher

# grep -E (OR)

```console
-E, --extended-regexp
             Interpret pattern as an extended regular expression (i.e., force grep to behave as egrep).
```

Find lines that contains "small is good" or "University".

```console
grep -E -n "small is good|University" history-of-unix.txt
```

> option -n was added to print the line that the pattern was found.

<img width="1505" alt="Screenshot 2023-11-24 at 12 44 09 p m" src="https://github.com/c4arl0s/grep/assets/24994818/c0be4705-bc41-4fad-aee1-252f2ba7fbeb">

# grep -E (AND)

```console
-E, --extended-regexp
             Interpret pattern as an extended regular expression (i.e., force grep to behave as egrep).
```

Find lines that contains "small is good" and "Unix".

```console
grep -E -n "small is good.*Unix" history-of-unix.txt
```

> option -n was added to print the line that the pattern was found.

<img width="1508" alt="Screenshot 2023-11-24 at 12 45 11 p m" src="https://github.com/c4arl0s/grep/assets/24994818/09abf002-4b80-4e37-8e55-a41f22e74179">

# grep -o (Prints only the matching part of the lines)

```console
-o, --only-matching
             Prints only the matching part of the lines.
```
Print strings that match a pattern over a line or lines. (example TXT-1245, TXT-123456, TXT-1234567, any size of the number)

Content of file.txt

```vim
TXT-1234, hdjsahdasdh, dhjsahdashdj TXT-5635261, 78327183, TXT-5621562, TXT-53625, etc 
TXT-1234, hdjsahdasdh, dhjsahdashdj TXT-5635261, 78327183, TXT-5621562, TXT-53625, etc 
```

Executing command:

```console
grep -o "TXT-[0-9]*" file.txt
```

Console output

```console
TXT-1234
TXT-5635261
TXT-5621562
TXT-53625
TXT-1234
TXT-5635261
TXT-5621562
TXT-53625
```
