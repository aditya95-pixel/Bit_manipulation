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

## Number of 1 Bits

Given a positive integer n, write a function that returns the number of set bits in its binary representation (also known as the Hamming weight).

```cpp
class Solution {
public:
    int hammingWeight(int x) {
        int cnt=0;
        while(x){
            x&=(x-1);
            cnt++;
        }
        return cnt;
    }
};
```

## Power of Two

Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.

```cpp
class Solution {
public:
    bool isPowerOfTwo(int x) {
        return (x>0 && (x & (x-1))==0);
    }
};
```

## Single Number

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int xoro=nums[0];
        for(int i=1;i<nums.size();i++)
        xoro^=nums[i];
        return xoro;
    }
};
```

## Missing Number

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int xoro=0;
        for(int i=1;i<=nums.size();i++)
        xoro^=i;
        for(int i=0;i<nums.size();i++)
        xoro^=nums[i];
        return xoro;
    }
};
```
