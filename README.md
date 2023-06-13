# grep

File pattern searcher

# grep OR

Find lines that contains "small is good" or "University".

```console
grep -E "small is good|University" history-of-unix.tx
```

<img width="1509" alt="Screenshot 2023-06-12 at 9 23 01 p m" src="https://github.com/c4arl0s/grep/assets/24994818/fa4a181f-b7bb-43a4-b6fe-a7c43a8868b6">

# grep AND

Find lines that contains "small is good" and "Unix".

```console
grep -E "small is good.*Unix" history-of-unix.txt
```

<img width="1512" alt="Screenshot 2023-06-12 at 9 26 44 p m" src="https://github.com/c4arl0s/grep/assets/24994818/32edebb0-6c63-487e-a9d6-054bf801d972">
