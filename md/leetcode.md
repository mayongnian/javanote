# leetcode笔记和题解

1. 两数之和  
法1 简单遍历  
法2 哈希表  
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int n = nums.length;
        Map <Integer,Integer> hashtable = new HashMap<Integer,Integer>();
        for(int i=0;i<n;++i) {
            if(hashtable.containsKey(target - nums[i])) {
                return new int[]{hashtable.get(target - nums[i]),i};
            }
            hashtable.put(nums[i],i);
        }
        return new int[0];
    }
}
```
返回简单数组  
```java
return new int[]{i,j};
return new int[0];  // default
```
for循环中使用i++还是++i?  
功能相同，++i的性能优于i++  
因为i++是使用当前值之后再加1，所以需要一个临时的变量来转存，++i则直接加1  

---
2. 两数相加  
