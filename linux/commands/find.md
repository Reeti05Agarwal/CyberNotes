# find

### use of . or /

. is used when you want to traverse the current directory

'/' is used when you what to traverse from the root directory

### Find File by Type

```
find [path] -type [type]
```

* **`-type f`**: Finds regular files.
* **`-type d`**: Finds directories.
* **`-type l`**: Finds symbolic links.

```
find . -type f
```

### Find file by size

```
find [path] -size [size]
```

**`[size]`**: Specifies the size. Use `c` for bytes, `k` for kilobytes, `M` for megabytes, etc.

**`+size`**: Greater than size.

**`-size`**: Less than size.

**`size`**: Exactly size.

### Find Files by name

```
find [path] -name "pattern"
```

### Find files by permission

```
find [path] -perm [mode]

find . -perm 644
```

### Find File by Owner

```
find [path] -user [username]

find . -user alice
```

### Find Fill by Group

```
find [path] -group [groupname]

find . -group admin
```

### Find File by Modification Time

```
find [path] -mtime [n]
```

**`-mtime [n]`**: Files modified exactly `n` days ago.

**`+n`**: Modified more than `n` days ago.

**`-n`**: Modified less than `n` days ago.

```
find . -mtime -7
```

### Find File by Access Time&#x20;

**`atime [n]`**: Files accessed exactly `n` days ago.

```
find [path] -atime [n]

find . -atime +30
```

### Execute Commands on Found Files

**`exec [command] {} +`**: Executes the specified command on each file found. `{}` is replaced by the filename.

```
find [path] [expression] -exec [command] {} +

find . -type f -exec chmod 644 {} +
```





