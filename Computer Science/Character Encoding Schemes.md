---
tags:
  - concept
  - encoding
---
Character encoding schemes **pack Character Code Numbers into *content bits* and unpack them back into character codes at the other end**.
# Fixed Width
Fixed-width encodings use a single width for all characters.
This means that while it can be **easier to process**, it is also **much more wasteful**.
## 8-Bit
This fixed-width encoding does as its name would suggest: **encoding every character using 8 bits**, no more, no less.
This means that the total code range is of 256 characters.
# Variable Width
Variable-width encodings **use different numbers of bits per character code numbers**.
This allows them to reduce the overall number of bits required for an entire character set.
It also allows more flexibility, by using multiple bytes for international characters.
## UTF-8
UTF-8 uses a non-modal, variable-length encoding for the character code values.
This works by **setting the leading bits of the first byte to the length of the encoded character**, in bytes.
# Modal Variable Width
A modal encoding uses special *escape patterns* to **shift between different *modes**.*
This makes them perfect at supporting complicated writing systems.