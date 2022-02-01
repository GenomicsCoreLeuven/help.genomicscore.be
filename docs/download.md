# How to download a large file?

Given a download link, one can use the tool [curl](https://en.wikipedia.org/wiki/CURL) to download a file through the command line interface:


**Getting information about the size and the expiration date:**
```sh
curl -I -L '<DOWNLOAD_LINK>'
```

**Downloadling**
```sh
curl -o /My/Locaction/some_file.zip '<DOWNLOAD_LINK>' 
```
