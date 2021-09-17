## Bit Mixing

use [prospector](https://github.com/skeeto/hash-prospector) to mine hash functions! blog post https://nullprogram.com/blog/2018/07/31/

The best that I can get is this

```console
$ ./prospector -8 -p xorr,mul,xorr,mul,xorr
```
```c
// score = 1.8931368037931986
uint64_t
hash(uint64_t x)
{
    x ^= x >> 33;
    x *= 0x9259090ada983f41;
    x ^= x >> 36;
    x *= 0x82c9d8bc574b8759;
    x ^= x >> 21;
    return x;
}
```

