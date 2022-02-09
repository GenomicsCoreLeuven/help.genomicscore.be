# How to interact with a Google Cloud Bucket

## Console / User Interface (UI)

### Downloading

![download](/assets/imgs/bucket_interaction_imgs/download.png)

### Do more with an object

!!! NOTE
    To do more than downloading an object requires elevated permissions; Storage Object Viewer+Creator or Storage Object Admin

![do_more](/assets/imgs/bucket_interaction_imgs/do_more.png)

### Copy / Move an object

![copy_move](/assets/imgs/bucket_interaction_imgs/copy_move.png)

### Moving an object in detail

![move_detail](/assets/imgs/bucket_interaction_imgs/move_detail.png)

### Granting / Revoking access

!!! info
    This is only allowed by elligible UZ Leuven employees cfr. [GC-MT113-PR](https://wiki.uz.kuleuven.ac.be/x/9wx9Fg)

## Terminal / Command Line Interface (CLI)

### Prerequisites

If you want to access the data through the Command Line Interface (CLI) please install gsutil on your device through the [Google Cloud SDK](https://cloud.google.com/sdk/#mac). More info on the gsutil usage can be found [here](https://cloud.google.com/storage/gsutil).

### Summary of typical commands

!!! info
    Replace the values in the curly braces {}


#### Listing files

```sh
# List
gsutil ls gs://{BUCKET_NAME}
```

```sh
# Example: List fastq files in a certain folder
gsutil ls gs://{BUCKET_NAME}/{FOLDER}/*.fastq.gz
```

#### Copy/Move files

```sh
# Copy
gsutil cp {src}/ {dst}/
```

```sh
# Example: from bucket to local machine
gsutil cp gs://{BUCKET_NAME}/{FILE_NAME} {/MY_DEVICE/FILE_DESTINATION/}
```

```sh
# Example: copy a set of csv files
gsutil cp gs://{BUCKET_NAME}/{FOLDER}/*.csv {/MY_DEVICE/FILE_DESTINATION/}
```

```sh
# Example: from your local machine to the bucket
gsutil cp {/MY_DEVICE/FILE_LOCATION/MY_FILE} gs://{BUCKET_NAME}/{OPTIONAL_BUCKET_FOLDER}
```

```
# Move; similar to Copy
gsutil mv {src}/ {dst}/
```

#### Syncing

One can use gsutil rsync to match source and destination (unidirectional)

```sh
gsutil -m rsync -r src/ dst/
```

#### Other

```sh
# Delete
gsutil rm gs://{BUCKET_NAME}/{FILE_NAME}
```

```sh
# Bucket size
gsutil du -sh gs://{BUCKET_NAME}
```

```sh
# File size
gsutil du -sh gs://{BUCKET_NAME}/{FILE_NAME}
```
