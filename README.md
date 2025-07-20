### 1.
Given a positive integer n, write a function that returns the number of set bits in its binary representation (also known as the Hamming weight).

```cpp
class Solution {
public:
    int hammingWeight(int n) {
        return __builtin_popcount(n);
    }
};
```

### 2.
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

### 3. 
Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.

```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n<=0)
        return false;
        while(n>0){
            if(n%2==0 || n==1)
            n/=2;
            else
            return false;
        }
        return true;
    }
};
```
