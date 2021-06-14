# Single-Number

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

 

_Example 1:_

`
Input: nums = [2,2,1]
`

`
Output: 1
`


_Example 2:_

`
Input: nums = [4,1,2,1,2]
`

`
Output: 4
`


_Example 3:_

`
Input: nums = [1]
`

`
Output: 1
`
 

_Constraints:_

`
1 <= nums.length <= 3 * 10^4
`

`
-3 * 10^4 <= nums[i] <= 3 * 10^4
`

Each element in the array appears twice except for one element which appears only once.

# Solution in Java

```
public int singleNumber(int[] nums) {
        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            if (map.containsKey(nums[i])) map.remove(nums[i]);
            else map.put(nums[i], 1);
        }

        return map.keySet().iterator().next();
    }
```


# Solution in JavaScript

```
var singleNumber = function(nums) {
    let singleNumber
    for (let i = 0; i < nums.length; i++) {
        if (nums.indexOf(nums[i]) === nums.lastIndexOf(nums[i])) {
            singleNumber = nums[i];
            break;
        }
    }
    
    return singleNumber;
};
```
# Solution in Python
```python
from collections import Counter
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        cnt = Counter(nums).items()
        for i in cnt:
            if i[1] == 1:
                return i[0]  
```