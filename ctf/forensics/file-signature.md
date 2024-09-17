# File Signature

File Magin Numbers

File signatures are unique sequences of bytes at the beginning of a file that can help identify its format or type. They’re often used to detect the file type or to ensure that a file hasn’t been corrupted or tampered with.&#x20;

### Use?

Files can sometimes come without an extension, or with incorrect ones. We use file signature analysis to identify the format (file type) of the file. Programs need to know the file type in order to open it properly. It's useful to analyze the file type before any forensics software.



Here are some common examples of file signatures:

1. **PDF Files**:
   * **Signature**: `%PDF-`
   * **Location**: The first few bytes of the file.
2. **JPEG Images**:
   * **Signature**: `FF D8 FF`
   * **Location**: At the start of the file.
3. **PNG Images**:
   * **Signature**: `89 50 4E 47 0D 0A 1A 0A`
   * **Location**: At the beginning of the file.
4. **ZIP Archives**:
   * **Signature**: `50 4B 03 04`
   * **Location**: At the start of the file.
5. **Executable Files (Windows .exe)**:
   * **Signature**: `4D 5A`
   * **Location**: The very beginning of the file (also known as the MZ header).
6. **Microsoft Word Documents (.doc)**:
   * **Signature**: `D0 CF 11 E0 A1 B1 1A E1`
   * **Location**: At the start of the file.
7. **MP3 Files**:
   * **Signature**: `49 44 33` (ID3 tag)
   * **Location**: At the beginning of the file.
8. **GZIP Compressed Files**:
   * **Signature**: `1F 8B`
   * **Location**: At the start of the file.

These signatures are useful in various contexts, such as malware detection, file recovery, and data validation. Tools and software often use these signatures to identify and process files appropriately.
