## Bit Mixing

use [prospector](https://github.com/skeeto/hash-prospector) to mine hash functions! blog post https://nullprogram.com/blog/2018/07/31/

The best that I can get is this:

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

- http://pod.tst.eu/http://cvs.schmorp.de/libecb/ecb.pod#BIT_MIXING_HASHING
- https://lists.sr.ht/~skeeto/public-inbox/%3Cda2c4c2dc0000b054e014636be12326a1a532ec5.camel%40opteya.com%3E
