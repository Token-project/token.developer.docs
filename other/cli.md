# cli snippets

## Generating an SHA-256 Hash From the Command Line

```text
echo -n "Do I need to prove myself again?" | openssl dgst -sha256
echo -n "Do I need to prove myself again?" | shasum -a 256
```

```text
openssl dgst -sha256 data.txt
shasum -a 256 data.txt
```



