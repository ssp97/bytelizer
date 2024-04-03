## Bytelizer
Bytelizer is a binary packaging/unpack library written in modern c, focusing on performance and light.

Feature:
 - Anchor for late data insert/fill
 - Barrier
 - Data prefix support
 - Static Protobuf structure declaration
 - Endianess

## Quick Guide
```c
typedef struct {
  uint16_t a;
  uint16_t b;
  uint32_t c;
} example_t;

// the generic way in c
example_t _example = {
  .a = 0x1234,
  .b = 0x5678,
  .c = 0xDEADBEEF
};

// the equivalent in bytelizer,
// allocates 64 bytes on the stack.
bytelizer_alloc(_ctx, 64); {
  bytelizer_put_uint16(_ctx, 0x1234);
  bytelizer_put_uint16(_ctx, 0x5678);
  bytelizer_put_uint32(_ctx, 0xDEADBEEF);
}

```

## LICENSE
Licensed under GPLv2 with ❤.