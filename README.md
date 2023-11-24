# grep

File pattern searcher

# grep -E (OR)

Find lines that contains "small is good" or "University".

```console
grep -E "small is good|University" history-of-unix.tx
```

<img width="1509" alt="Screenshot 2023-06-12 at 9 23 01 p m" src="https://github.com/c4arl0s/grep/assets/24994818/fa4a181f-b7bb-43a4-b6fe-a7c43a8868b6">

# grep -E (AND)

Find lines that contains "small is good" and "Unix".

```console
grep -E "small is good.*Unix" history-of-unix.txt
```

<img width="1512" alt="Screenshot 2023-06-12 at 9 26 44 p m" src="https://github.com/c4arl0s/grep/assets/24994818/32edebb0-6c63-487e-a9d6-054bf801d972">

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
