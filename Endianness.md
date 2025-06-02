- A **word** is typically 16 bits (2 bytes).
- A **double word (dword)** is 32 bits (4 bytes).
- A **quadruple word (qword)** is 64 bits (8 bytes).
- These terms describe the size of data units in memory and affect how endianness applies to them.
## MSB and LSB

>**MSB (Most Significant Byte/Bit)** is the byte/bit in a multi-byte/bit number that holds the **highest value** or weight.

For example, in the hexadecimal number `0x12345678`, the MSB is `0x12`.

>**LSB (Least Significant Byte/Bit)**: The byte or bit with the lowest value or weight. 

In `0x12345678`, the LSB is `0x78`.
## Endianness

>**Endianness** refers to the order in which bytes of a multi-byte data type (like a 16-bit word, 32-bit double word, etc.) are stored in memory.

There are two main types of endianness:

>**Big-endian**: Stores the **MSB** at the **lowest memory address** (first). So, the bytes are stored from most significant to least significant as memory addresses *increase*.
    
>**Little-endian**: Stores the **LSB** at the **lowest memory address** (first). So, bytes are stored from least significant to most significant as memory addresses increase

Suppose you have a 32-bit hexadecimal number: `0x12345678`.

| **Big-endian** |              | **Little-endian** |              |
| -------------- | ------------ | ----------------- | ------------ |
| **Addess**     | **Value**    | **Addess**        | **Value**    |
| `a`            | `0x12` (MSB) | `a`               | `0x78` (LSB) |
| `a + 1`        | `0x34`       | `a + 1`           | `0x56`       |
| `a + 2`        | `0x56`       | `a + 2`           | `0x34`       |
| `a + 3`        | `0x78` (LSB) | `a + 3`           | `0x12` (MSB) |
This means the same number appears reversed in memory depending on the endianness.

## Translating between bug and little endian

To convert a multi-byte number from big-endian to little-endian (or vice versa), you reverse the byte order. For example:

- Big-endian: `0x12 34 56 78`
- Little-endian: `0x78 56 34 12`

https://moodledaszczuk.vizja.pl/mod/quiz/attempt.php?attempt=54844&cmid=1327&page=4

## Examples

### `#53` in Little-endian

>The byte value is `#53`
>Give the representation of this byte as a byte in Little-endian. Suppress the `#` before the hexadecimal number.

- **Endianness** (big or little) **only applies to multi-byte data types** (like 16-bit, 32-bit, etc.).
- So, the answer is `#53`.

### Double word in Little-endian

>The double word value is `#33542077`
>Give the representation of this double word as a quadruple word in Little-endian. Suppress the # before the hexadecimal number.

| Given                     | Little-endian                        | Given                     | Big-endian                |
| ------------------------- | ------------------------------------ | ------------------------- | ------------------------- |
| Byte<br>`24`              | Quadruple word<br>`2400000000000000` | Byte<br>`53`              | Byte<br>`53`              |
| Byte <br>`24`             | Word<br>`8700`                       | Double word<br>`70328712` | Double word<br>`70328712` |
| Double word<br>`33542077` | Quadruple word<br>`7720543300000000` | Byte <br>`21`             | Word<br>`0021`            |
| Byte<br>`67`              | Double word<br>`67000000`            | Byte <br>`65`             | Double word<br>`00000065` |
