# Steganography

Tasked with finding information hidden in files or images

### **Common Techniques:**

1. **Files in Images:**
   * **Concept**: You can hide files within an image file. For example, a ZIP file can be appended to a JPEG image. The image will display normally, but hidden data can be extracted.
   * **How It Works**: Image files have specific bytes that denote the start and end of the image data. For JPEGs, the end marker is `FF D9`. Anything after this can be additional data.
   * **Extraction Method**: Use tools like `xxd` (for viewing hex dumps) and `dd` (for extracting hidden files).
     * Example Command: `dd if=image.jpg bs=1 skip=1972141 of=hidden.zip` (convert hex offset to decimal).
2.  **Hidden Text in Images:**

    * **Concept**: Text can be hidden within an image using subtle color changes or low opacity, making it nearly invisible.
    * **Extraction Tools**:
      * **GIMP or Photoshop**: Apply filters to reveal hidden text.
      * **Stegsolve**: Use various color filters to uncover hidden data.
      * **Scripts**: Use scripts to adjust colors and reveal text.



### **Steganography Example**:

* **File**: `example.jpg` containing hidden data.
* **Procedure**: Open the image in a hex editor to find the JPEG end marker (`FFD9`) and look for any data following it. Extract using `dd`.







