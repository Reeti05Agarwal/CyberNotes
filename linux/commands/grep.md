# grep



Search for a pattern in a file.

This command will search for the “_pattern_” in file.

If any lines in the file contain the word "_Pattern_", **`grep`** will display those lines as output.

If there are multiple occurrences on different lines, each matching line will be shown.

If there are no matches, the command will produce no output.

```jsx
grep pattern filename
```

examples

```c
grep So <file>
```

so it will display all the things containg with “So” in \<file>.

Grep is case sensitive, so to remove it for convenience, we use `-i`:

```c
grep -i So <file>
```

To output the negation of the pattern, that is u want everything but the pattern:

`-v`

```c
grep -v So <file>
```

Allows us to search the contents of files for specific values that we are looking for.

***

We can use `grep`to search the entire contents of this file for any entries of the value that we are searching for. Going with the example of a web server's access log, we want to see everything that the IP address "81.143.211.90" has visited (note that this is fictional)

```c
tryhackme@linux1:~$ grep "81.143.211.90" access.log
81.143.211.90 - - [25/Mar/2021:11:17 + 0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0 (Linux; Android 7.0; Moto G(4))"
tryhackme@linux1:~$
```

***
