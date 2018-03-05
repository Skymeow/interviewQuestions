Given an arraySofnintegers, are there elementsa,b,cinSsuch thata+b+c= 0? Find all unique triplets in the array which gives the sum of zero.

**Note:**The solution set must not contain duplicate triplets.

```
For example, given array S = [-1, 0, 1, 2, -1, -4],

A solution set is:
[
  [-1, 0, 1],
  [-1, -1, 2]
]
```

solution: 

```
class Solution:
    def threeSum(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        inner_arr = []
        outter_arr = []
        left_check = 0
        right_check = len(s) - 1
        while right_check > 0:
            for i, v in enumerate(s):
                left_check = i
                if s[left_check] + s[i+1] == abs(s[right_check]):
                    match = [s[i], s[i+1], s[right_check]]
                    inner_arr.extends(match)
                    right_check -= 1
                else:
                    for mid, mid_v in enumerate(s):
                        if s[left_check] + s[mid] == abs(s[right_check]):
                            match = [s[left_check], s[mid], s[right_check]]
                            inner_arr.extends(match)
                            right_check -= 1
                        else:
                            continue
        outter_arr.append(inner_arr)
        return outter_arr
```



