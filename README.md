# grep

File pattern searcher

```swift
SYNOPSIS
     grep [-abcdDEFGHhIiJLlMmnOopqRSsUVvwXxZz] [-A num] [-B num] [-C num] [-e pattern] [-f file] [--binary-files=value] [--color[=when]]
          [--colour[=when]] [--context=num] [--label] [--line-buffered] [--null] [pattern] [file ...]
```

# Example

- Find all occurrences of the pattern ‘patricia’ in a file:

```console
grep 'patricia' myfile
```
- Same as above but looking only for complete words:

```console
grep -w 'patricia' myfile
```
- Count occurrences of the exact pattern ‘FOO’ :

```console
grep -c FOO myfile
```
- Same as above but ignoring case:

```console
$ grep -c -i FOO myfile
```
- Find all occurrences of the pattern ‘.Pp’ at the beginning of a line:

```console
grep '^\.Pp' myfile
```

The apostrophes ensure the entire expression is evaluated by grep instead of by the user's shell.  The caret ‘^’ matches the null string at the beginning of a line, and the ‘\’ escapes the ‘.’, which would otherwise match any character.

- Find all lines in a file which do not contain the words ‘foo’ or ‘bar’:

```console
grep -v -e 'foo' -e 'bar' myfile
```

- Peruse the file ‘calendar’ looking for either 19, 20, or 25 using extended regular expressions:

```console
egrep '19|20|25' calendar
```

-  Show matching lines and the name of the `‘*.h’` files which contain the pattern `‘FIXME’`.  Do the search recursively from the `/usr/src/sys/arm directory`

```console
grep -H -R FIXME --include="*.h" /usr/src/sys/arm/
```

- Same as above but show only the name of the matching file:

```console
grep -l -R FIXME --include="*.h" /usr/src/sys/arm/
```

- Show lines containing the text ‘foo’.  The matching part of the output is colored and every line is prefixed with the line number and the offset in the file for those lines that matched.

```console
grep -b --colour -n foo myfile
```
- Show lines that match the extended regular expression patterns read from the standard input:

```console
echo -e 'Free\nBSD\nAll.*reserved' | grep -E -f - myfile
```

- Show lines from the output of the pciconf(8) command matching the specified extended regular expression along with three lines of leading context and one line of trailing context:

```console
pciconf -lv | grep -B3 -A1 -E 'class.*=.*storage'
```
- Suppress any output and use the exit status to show an appropriate message:

```console
grep -q foo myfile && echo File matches
```

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
