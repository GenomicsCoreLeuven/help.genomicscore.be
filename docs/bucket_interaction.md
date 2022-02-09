# How to interact with a Google Cloud Bucket

## Console / User Interface (UI)

### Downloading

![download](/docs/assets/imgs/bucket_interaction_imgs/download.png)

### Do more with an object

> NOTE: to do more that downloading an object requires elevated permissions, Storage Object Viewer+Creator or Storage Object Admin

![do_more](/docs/assets/imgs/bucket_interaction_imgs/do_more.png)

### Copy / Move an object

![copy_move](/docs/assets/imgs/bucket_interaction_imgs/copy_move.png)

### Moving an object in detail

![move_detail](/docs/assets/imgs/bucket_interaction_imgs/move_detail.png)

### Granting / Revoking access

This is only allowed by elligible UZ Leuven employees cfr. [GC-MT113-PR](https://wiki.uz.kuleuven.ac.be/x/9wx9Fg)

## Terminal / Command Line Interface (CLI)

### Prerequisites

If you want to access the data through the Command Line Interface (CLI) please install gsutil on your device through the [Google Cloud SDK](https://cloud.google.com/sdk/docs/#mac). More info on the gsutil usage can be found [here](https://cloud.google.com/storage/docs/gsutil).

### Summary of typical commands

_Replace the values in the curly braces {}_

```sh
# List
gsutil ls gs://{BUCKET_NAME}

# List fastq files in a certain folder
gsutil ls gs://{BUCKET_NAME}/{FOLDER}/*.fastq.gz

# Copy
gsutil cp {src}/ {dst}/

# Example: from bucket to local machine
gsutil cp gs://{BUCKET_NAME}/{FILE_NAME} {/MY_DEVICE/FILE_DESTINATION/}

# Example: from your local machine to the bucket
gsutil cp {/MY_DEVICE/FILE_LOCATION/MY_FILE} gs://{BUCKET_NAME}/{OPTIONAL_BUCKET_FOLDER}

# Move similar to Copy
gsutil mv {src}/ {dst}/

# Rsync
gsutil -m rsync -r src/ dst/

# Delete
gsutil rm gs://{BUCKET_NAME}/{FILE_NAME}

# Bucket size
gsutil du -sh gs://{BUCKET_NAME}

# File size
gsutil du -sh gs://{BUCKET_NAME}/{FILE_NAME}
```
