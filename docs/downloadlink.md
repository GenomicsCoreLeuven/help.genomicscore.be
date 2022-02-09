# How to handle a download link

Requested datasets can be quite large, depending on the type of experiment.

Given a download link, one can use the tool [curl](https://en.wikipedia.org/wiki/CURL) to download a file through the command line interface:

**Getting information:**

```sh
curl -I -L '<DOWNLOAD_LINK>'
```

**Downloading**

```sh
curl -o /My/Locaction/some_file.tar.gz '<DOWNLOAD_LINK>'
```

**Extracting**

```sh
tar -xzvf /My/Locaction/some_file.tar.gz
```
