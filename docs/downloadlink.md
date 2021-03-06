# How to handle a download link

Requested datasets can be quite `large`, depending on the type of experiment.

Given a download link, one can use the tool [curl](https://en.wikipedia.org/wiki/CURL) to download a file through the command line interface instead. Another tool is [wget](https://www.gnu.org/software/wget/).

!!! warning "Warning"
    Always ensure you understand the commands you execute to avoid unintended behaviour.

## Example with [curl](https://en.wikipedia.org/wiki/CURL)

!!! info ""
    Please replace the values in `curly brackets {}` (also remove the brackets)

=== "macOS"

    ```sh
    # curl, md5 and unzip should be preinstalled

    # Downloading
    curl -o {/My/Locaction/some_file.zip} '{DOWNLOAD_LINK}'

    # Verify MD5 hash to ensure no corruption occured
    md5 {/My/Locaction/some_file.zip}

    # Extracting
    unzip {/My/Locaction/some_file.zip}
    ```

=== "Linux"

    ```sh
    # Update dependencies
    sudo apt update

    # Install curl
    sudo apt -y install curl

    # Install zip and unzip
    sudo apt install zip unzip

    # Downloading
    curl -o {/My/Locaction/some_file.zip} '{DOWNLOAD_LINK}'

    # Verify MD5 hash to ensure no corruption occured
    md5sum {/My/Locaction/some_file.zip}

    # Extracting
    unzip {/My/Locaction/some_file.zip}
    ```

=== "Windows"

    If not on your machine, please install through the [official curl website](https://curl.se/windows/)

    ```PowerShell
    # Verify
    Get-Command curl.exe

    # Downloadling
    curl.exe -o {C:\My\Locaction\some_file.zip} '{DOWNLOAD_LINK}'

    # Verify MD5 hash to ensure no corruption occured
    Get-FileHash {C:\My\Locaction\some_file.zip} -Algorithm MD5 

    # Extracting
    Expand-Archive {C:\My\Locaction\some_file.zip} -DestinationPath {C:\My\Locaction\Unzipedfolder} -Verbose
    ```
