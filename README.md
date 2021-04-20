# HW6 extension

For this "extension" you'll once again process a large compressed text file. To receive full credit you must satisfy the following:

* Your solution must use argparse, not hard-coded paths.
* Your solution must not use the `.read`, `.readline`, or `.readlines` methods on file-like objects.
* Your solution must not store intermediate sentences in a list (or any other container);
  once you are done processing a sentence/line, you must print that line to the output file *immediately*.

## What to do

1. Download the following *enormous* English text file at the command line as follows:

    ```bash
    curl -O http://data.statmt.org/news-crawl/en/news.2013.en.shuffled.deduped.gz
    ```

Like before, this is a gzip-ed text file in which each line is a sentence, but it is roughly ten times larger than the 2007 data.
2. Write an executable Python script `donbas.py`. This script should open an user-specified input gzip file, 
and for each line, print to a user-specified output file any sentence which contain the tokens (not merely substrings) `Bayer` or `aspirin`. You should print the sentences as they appear in the original document, not tokenized or case-folded.

## Test support

The resulting file should have 2,647 lines:

```bash
$ ./bayer.py news.2013.en.shuffled.deduped.gz bayer-aspirin.txt
$ wc -l bayer-aspirin.txt
2647 bayer-aspirin.txt
```

## Hints

* Check that you're conforming to the "rules" above.
* This file may take a long time to download, and the script a long time to run. Start early, and let them run overnight or while you're doing something else.
* You should not print a line twice, even if contains multiple instances of the two keywords.
