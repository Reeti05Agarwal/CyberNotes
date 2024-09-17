# openssl



## Base64

```
echo -n "Hello, World!" | openssl base64
```

```
echo "SGVsbG8sIFdvcmxkIQ==" | openssl base64 -d
```

## Encrypting and Decrypting

```
openssl enc -aes-256-cbc -salt -in plaintext.txt -out encrypted.enc
```

```
openssl enc -d -aes-256-cbc -in encrypted.enc -out decrypted.txt
```







