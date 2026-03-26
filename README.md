# phrase_u64

Converts an unsigned 64 bits integer into a phrase that is "hopefully" easier to remember. 

## For what purpose ?

Could be used to memorize/encode 64bits UID or 64bits IP address.

## Example :

```python
from phrase_u64 import u64_to_phrase

# for Micropython compatibilility :
def rand_u64() :
    from random import getrandbits
    return getrandbits(32) << 32 | getrandbits(32)

for i in range(0,5):
    u64 = rand_u64()
    phrase = u64_to_phrase( u64 )
    print( "{0} : {1}".format( hex(u64) , phrase ) ) 
```

Should print something like :

```
0x1da023ff0bed82af : On planet Venus, the name of the curious bronze hare who is swiftly coloring the tenth zombie bowl is Karen the fourth.
0x3206a74ead15e8e0 : On planet Mars, the name of the strange lime lion who is briefly recycling the eighth sandy lamp is Betty the elegant.
0xd8a91d7315a182fa : On planet Makemake, the name of the eighth brown hare who is politely flipping the feral electric attic is Mark the super.
0x8c3d499721131740 : On planet Ceres, the name of the agile gray shark who is bravely mixing the sleepy fuchsia charger is Thomas the stealth.
0x3742c7d4863af33a : On planet Mars, the name of the eighth brunette salmon who is currently building the great white pillow is Andrew the slow.
```

## TODO :
- `phrase_to_u64()` decoder
- find an alternative phrase format and vocabulary easier to remember

## Source of inspiration :
- https://en.wikipedia.org/wiki/What3words
