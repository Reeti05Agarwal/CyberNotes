# Netcat (nc)

* **Purpose**: Useful for reading and writing data across network connections using TCP or UDP.
* **Usage**: Can be used for interacting with services that are not HTTP-based or for simple network interactions.
* Swiss army knife if networking



* To create a basic TCP connection to a remote server:

```
 nc [hostname] [port]
 
 nc example.com 80
```

* For UDP, use the `-u` flag:

```
nc -u [hostname] [port]

nc -u example.com 12345
```

* To scan a range of ports on a target:

`-z`: Zero-I/O mode (just scan for open ports)

`-v`: Verbose mode (shows detailed information)

```
nc -zv [hostname] [start_port]-[end_port]

nc -zv example.com 1-1000
```













