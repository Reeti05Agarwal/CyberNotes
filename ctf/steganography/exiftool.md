# Exiftool



`exiftool` is a powerful command-line utility for reading, writing, and editing metadata in image files and other file types. It supports a wide range of metadata formats, including EXIF, IPTC, XMP, and more. Here’s an overview of its features and usage:

#### Key Features of `exiftool`:

1. **Read Metadata**: Extract metadata from images and other files, including camera settings, GPS information, and timestamps.
2. **Write Metadata**: Modify or add metadata to files.
3. **Delete Metadata**: Remove specific metadata tags or all metadata from a file.
4. **Batch Processing**: Apply changes to multiple files at once.
5. **Support for Many Formats**: Handles a broad range of file types, not just images but also PDFs, videos, and other media.
6. **Versatile Output**: Can output metadata in various formats, including XML, JSON, and human-readable text.

#### Basic Usage:

**1. Viewing Metadata:** To view metadata from a file, use:

```bash
exiftool filename.jpg
```

**2. Editing Metadata:** To change metadata, such as the author or date, use:

```bash
exiftool -Author="Your Name" -DateTimeOriginal="2024:01:01 12:00:00" filename.jpg
```

**3. Batch Processing:** To apply changes to multiple files, use:

```bash
exiftool -Author="Your Name" *.jpg
```

**4. Deleting Metadata:** To remove all metadata from a file:

```bash
exiftool -all= filename.jpg
```

**5. Writing to Specific Tags:** To write to a specific tag, like GPS coordinates:

```bash
exiftool -GPSLatitude=37.7749 -GPSLongitude=-122.4194 filename.jpg
```

#### Installation:

**On Debian-based systems (like Ubuntu):**

```bash
sudo apt-get install libimage-exiftool-perl
```

**On Fedora:**

```bash
sudo dnf install exiftool
```

**On Arch Linux:**

```bash
sudo pacman -S exiftool
```

**On macOS (using Homebrew):**

```bash
brew install exiftool
```

`exiftool` is a versatile and indispensable tool for photographers, archivists, and anyone who needs to manage or analyze metadata in their files.





