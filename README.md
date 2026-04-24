## Problem Description
Merge two sorted integer arrays `nums1` and `nums2` into `nums1` as a single sorted array. `nums1` has a total capacity of `m + n` to accommodate all elements.
## Solution
This approach uses a **three-pointer** technique starting from the **back** of the arrays to ensure $O(1)$ space complexity without overwriting existing data.
- **Time Complexity:** $O(m + n)$
- **Space Complexity:** $O(1)$
## Implementation (Java)
```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1, j = n - 1, k = m + n - 1;
        while (i >= 0 && j >= 0) {
            nums1[k--] = (nums1[i] > nums2[j]) ? nums1[i--] : nums2[j--];
        }
        while (j >= 0) {
            nums1[k--] = nums2[j--];
        }
    }
}

