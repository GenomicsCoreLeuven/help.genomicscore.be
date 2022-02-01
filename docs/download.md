# How to download a large file?

Given a download link, one can use the tool [curl](https://en.wikipedia.org/wiki/CURL) to download a file through the command line interface:


```sh
# Getting information about the size and the experiation date:
curl -I -L '<DOANLOAD_LINK>'

# Downloadling:
curl -o /My/Locaction/some_file.zip '<DOANLOAD_LINK>' 
```
