Welcome to the topic of data compression! Before our live session, please go through the material below. This will introduce you to the fundamental concepts of why and how we make files smaller.

## What is Data Compression?

At its core, data compression is the process of encoding information using fewer bits than the original representation. Think of it like creating a shorthand for frequently used phrases. Instead of writing "Laugh Out Loud" every time, we often use "LOL". Compression algorithms do something similar but for digital data (text, images, videos, etc.).

Why do we compress data? There are two main reasons:

1. **Saving Storage Space:** Compressed files take up less disk space, allowing us to store more data on our devices or in the cloud.
2. **Faster Data Transfer:** Smaller files transmit more quickly over networks (like the internet), saving time and bandwidth. This is crucial for everything from downloading software to streaming videos.

In cybersecurity, understanding compression is important. Log files are often compressed to save space, malware might be compressed to evade detection, and compressed archives are common ways to package and transfer data, sometimes containing malicious payloads.

## Lossless vs. Lossy Compression

![image.png](attachment:814afed3-b59e-4ecd-b3d5-bcee643d3af1:image.png)

There are two main categories of compression algorithms:

1. **Lossless Compression:** This method reduces file size without losing _any_ original data. When you decompress a file compressed with a lossless algorithm, you get back an exact copy of the original. This is essential for data where perfect accuracy is critical, such as:
    - Text documents (code, articles, books)
    - Executable programs
    - Log files
    - Certain image formats (like PNG or GIF) where perfect fidelity is needed. Common lossless formats include ZIP, Gzip (.gz), Bzip2 (.bz2), and XZ (.xz).
2. **Lossy Compression:** This method achieves much higher compression ratios (meaning much smaller files) by _permanently discarding_ some data that is considered less important or less noticeable to human perception. When you decompress a lossy file, you get back something _very similar_ to the original, but not identical. This is acceptable for data where perfect accuracy isn't the primary goal, and some loss of quality is a reasonable trade-off for significantly smaller file sizes. Examples include:
    - Images (JPEG/JPG)
    - Audio (MP3, AAC)
    - Video (MP4, AVI using specific codecs) The algorithm decides which bits of information are less critical. For example, in a photo, it might discard subtle variations in color that the human eye wouldn't easily detect. In audio, it might remove frequencies outside the typical range of human hearing.

### Think about it

When would using lossy compression be a really bad idea in a cybersecurity context? When might it be acceptable or even necessary?

## How Does Lossless Compression Work?

Lossless compression algorithms work by finding and eliminating statistical redundancy. They don't throw away information; they just represent it more efficiently. Here are a couple of simplified ideas behind common techniques:

- **Run-Length Encoding (RLE):** Imagine a line in an image that is just 100 white pixels in a row. Instead of storing "white, white, white, ... (100 times)", RLE stores something like "100 white". It replaces sequences of repeating data with a count and a single instance of the data.

```
Original Image Line:
⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪

Compressed with RLE:
"20 × ⚪"
```

- **Dictionary Coding (e.g., LZ77/LZ78 family used in Gzip, ZIP):** These algorithms build a "dictionary" of data sequences encountered so far. When a sequence reappears, instead of writing the sequence again, the algorithm writes a short reference (a pointer) to its previous occurrence in the dictionary. For example, if the phrase "the quick brown fox" appears multiple times in a document, the compressor might store it fully the first time and then use short pointers for subsequent occurrences.

```
Original Text:
"the quick brown fox jumps over the lazy dog. the quick brown fox sleeps."

Step 1: Build a dictionary of repeated sequences.
[1] = "the quick brown fox"

Step 2: Replace repeated sequences with references.

Compressed Text:
[1] jumps over the lazy dog. [1] sleeps.
```

## Archiving vs. Compression

It's common to encounter `.tar.gz` or `.zip` files. These often involve two related but distinct concepts:

- **Archiving:** This is the process of combining multiple files and directories into a single file (the archive). This makes it easier to manage and transfer groups of files. The `tar` (Tape Archive) command on Unix-like systems is a classic example. Archiving _itself_ does not necessarily compress the data, although some archive formats might include compression.
- **Compression:** This is the process of reducing the size of data, as discussed above. Tools like `gzip`, `bzip2`, or `xz`typically operate on a _single_ file or data stream.

Often, these two steps are combined. For example:

1. `tar` is used to bundle multiple files/directories into a single `.tar` archive file.
2. `gzip` is then used to compress that single `.tar` file, resulting in a `.tar.gz` file.

ZIP files (`.zip`) are a common format that typically combines both archiving and compression into a single step and format.

## Common Compression Tools on macOS/Linux

Your Mac comes with command-line tools for handling common compression formats:

- **`gzip` / `gunzip`:** One of the most common lossless compression tools (`.gz` files). `gzip` compresses, `gunzip`decompresses.
- **`bzip2` / `bunzip2`:** Another lossless compression tool, often achieving better compression than `gzip` but sometimes slower (`.bz2` files).
- **`xz` / `unxz`:** A more modern lossless compression tool, often providing the best compression ratios but can be slower, especially for compression (`.xz` files).
- **`tar`:** Used for archiving (bundling files). It has options to call compression tools directly (e.g., `tar -czf archive.tar.gz files...` creates a gzipped tar archive).
- **`zip` / `unzip`:** Handles `.zip` archives, which combine archiving and compression.

### Try it yourself

1. Open your Terminal application (you can find it using Spotlight search - press `Cmd + Space` and type "Terminal").
    
2. Create a simple text file. Type the following command and press Enter:
    
    ```
    echo "This is a test file. Repetition is the key to compression. Repetition is the key to compression. Repetition is the key to compression." > test.txt
    ```
    
3. Check the size of the file:
    
    ```
    ls -l test.txt
    ```
    
    Note the size in bytes (the number before the date).
    
4. Compress the file using `gzip`:
    
    ```
    gzip test.txt
    ```
    
5. List the files again. What is the new file name? Check its size:
    
    ```
    ls -l test.txt.gz
    ```
    
    How does the size compare to the original?
    
6. Decompress the file:
    
    ```
    gunzip test.txt.gz
    ```
    
7. Check the contents to ensure it's the same as the original:
    
    ```
    cat test.txt
    ```
    

You've just performed lossless compression and decompression!

That's the basic introduction to compression. We'll explore these concepts and tools more interactively in the live session.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-12-Compression-qxssczohrjyityd?mode=doc](https://gamma.app/docs/Technical-Foundations-12-Compression-qxssczohrjyityd?mode=doc)

Try not to peek before class - spoilers inside!

</aside>