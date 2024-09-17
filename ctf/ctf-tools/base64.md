# Base64

[Base64](https://en.wikipedia.org/wiki/Base64)

used **to encode binary data as printable text of set of 64 different ASCII characters**. This allows you to transport binary over protocols or mediums that cannot handle binary data formats and require simple text.

represent [binary data](https://en.wikipedia.org/wiki/Binary\_data) (more specifically, a sequence of 8-bit [bytes](https://en.wikipedia.org/wiki/Byte)) in sequences of 24 [bits](https://en.wikipedia.org/wiki/Bit) that can be represented by four 6-bit Base64 digits.

ability to embed [image files](https://en.wikipedia.org/wiki/Image\_files) or other binary assets inside textual assets such as [HTML](https://en.wikipedia.org/wiki/HTML) and [CSS](https://en.wikipedia.org/wiki/CSS) files.

Base64 is also widely used for sending [e-mail](https://en.wikipedia.org/wiki/E-mail) attachments. This is required because [SMTP](https://en.wikipedia.org/wiki/Simple\_Mail\_Transfer\_Protocol) – in its original form – was designed to transport [7-bit ASCII](https://en.wikipedia.org/wiki/7-bit\_ASCII) characters only. This encoding causes an overhead of 33–37% (33% by the encoding itself; up to 4% more by the inserted line breaks).

Each character in the Base64 encoding represents 6 bits of the original binary data.

### How to identify if its base64:

1. **Check for Padding**: Base64-encoded strings are often padded with one or two equal signs ('=') at the end. If you see one or two equal signs at the end of the text, it's a strong indicator of Base64 encoding.
2. **Length**: Base64-encoded data typically has a length that is a multiple of 4 characters. If the length of the text is not a multiple of 4, it might not be Base64 encoded.
3. **Character Set**: Base64-encoded data only contains a specific set of characters, usually letters (both uppercase and lowercase), digits, '+', '/', and '=' for padding. If you see any other characters, it's likely not Base64.
4.  **Decoding Attempt**: Try to decode the text using a Base64 decoding tool or a programming language/library that supports Base64 decoding. If it successfully decodes into binary data or text, then it's likely Base64 encoded.

    [Base64 Decode and Encode - Online](https://www.base64decode.org/)
5. **Context**: Sometimes, the context in which you encounter the text can be a clue. If you're dealing with data transmission or storage, and the data is supposed to be binary, there's a higher chance it's Base64 encoded.
