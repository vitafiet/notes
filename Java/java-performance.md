# Java memory layout information

- Any Java Object occupies at least 16 bytes, 12 out of which are occupied by a Java object header.
- All Java objects are aligned by 8 bytes boundary.

**Example:** an object containing 2 fields: `int` and `byte` will occupy not 17 (12 + 4 + 1), but 24 bytes (17 aligned by 8 bytes).

- Each Object reference occupies 4 bytes if the Java heap is under 32G (and `XX:+UseCompressedOops` is turned on - by default, it is turned on in the recent Oracle JVM versions). Otherwise, Object references occupy 8 bytes.

- Arrays consume 12 bytes + their length multiplied by their element size ( + of course, rounded by 8 bytes alignment).

- `String` contains 3 fields – a `char[]` with the string data plus 2 `int` fields with 2 hash codes calculated by the different algorithms. It means that a `String` itself needs 12 (header) + 4 (`char[]` reference) + 4 * 2 (int) = 24 bytes.\
Besides that, a `char[]` with the string data occupies 12 + length * 2 bytes (plus alignment).\
It means that a `String` occupies 36 + length*2 bytes (aligned by 8 bytes).

## Primitive types and their memory requirements:
```
byte, boolean	|   1 byte
short, char	    |   2 bytes
int, float	    |   4 bytes
long, double	|   8 bytes
```

## Wrappers memory requirements:
Numeric wrappers occupy 12 bytes plus size of the underlying type (plus 8-byte alignment if needed).
```

Byte, Boolean	    |   16 bytes
Short, Character	|   16 bytes
Integer, Float	    |   16 bytes
Long, Double	    |   24 bytes
```

## General Java memory optimization tips

- Prefer primitive types to their Object wrappers.
- Try to minimize number of Objects you have.
- Prefer array-based structures like `ArrayList`/`ArrayDeque` to pointer based structures like `LinkedList`.



