# FitGirl Repacks Batch Downloader

This Python script automates the process of extracting and downloading file parts from [FitGirl Repacks](https://fitgirl-repacks.site/). It specifically targets and scrapes `fuckingfast.co` mirror links from a provided game page, batches the downloads, and organizes the output files into structured directories.

## Features

* **Automated Link Scraping:** Provide a FitGirl Repack URL, and the script automatically extracts all associated `fuckingfast.co` download links.
* **Resume Capability:** The script logs pending links in an `input.txt` file and removes them upon successful download. If your session is interrupted, you can restart the script to resume exactly where you left off.
* **Auto-Organization:** Downloads are automatically saved into a newly generated `downloads/[game_name]` folder based on the URL metadata.
* **Visual Progress Tracking:** Integrates `tqdm` to display real-time, detailed progress bars, file sizes, and download speeds.
* **Custom Console Logging:** Uses `colorama` to provide a clean, color-coded, and timestamped terminal output for tracking successes, errors, and system warnings.

## Prerequisites

You will need Python 3 installed on your system. The script relies on a few external libraries that handle HTTP requests, HTML parsing, and console visuals. 

Install the required dependencies using pip:

```bash
pip install -r requirements
```

## Usage

1.  Open your terminal or command prompt and navigate to the directory where the script is saved.
2.  Execute the script:

```bash
python main.py
```

### Starting a New Download
When the script runs, it will prompt you with: `Enter Fitgirl Game Link (leave empty to resume from input.txt):`
Paste the full URL of the FitGirl Repack game page and press Enter. The script will scrape the links, populate `input.txt`, create the download directory, and begin fetching the files.

### Resuming an Interrupted Download
If your script crashes, loses connection, or is manually stopped, your remaining links are still safely stored in `input.txt`. 
To resume, run the script again. When prompted for the URL, **leave it blank and press Enter**. The script will automatically read the remaining URLs from the text file and continue the batch download.

## Limitations

* **Specific Host:** This script is hardcoded to look exclusively for `fuckingfast.co` mirror links. If a game page does not use this specific file host, the script will return a "No Matching URLs Found" error.
* **Disk Space:** The script currently does not check for available disk space before initiating large file downloads.

## Disclaimer

This script interacts with live web pages and third-party file-hosting services. Changes to the DOM structure of the source website or the file host's download logic may break the scraping functionality. 
