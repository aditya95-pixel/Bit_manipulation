# Bit manipulation concepts

## Bit operators

```txt
&   // AND
|   // OR
^   // XOR
~   // NOT
<<  // left shift
>>  // right shift
```

## Golden rules

```txt
x^x=0
x^0=x
x & -x → gives lowest set bit
x & (x - 1) → removes lowest set bit
Power of two checking → x > 0 && (x & (x - 1)) == 0
```

## Essential Bit Operations

```cpp
// check ith bit
bool on = (x >> i) & 1;

// set ith bit
x |= (1 << i);

// clear ith bit
x &= ~(1 << i);

// toggle ith bit
x ^= (1 << i);

// count set bits
while (x) {
    x &= (x - 1);
    cnt++;
}
```
