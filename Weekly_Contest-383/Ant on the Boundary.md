## 100214. Ant on the Boundary

<details>
<summary>Java</summary>

```java

// An ant is on a boundary. It sometimes goes left and sometimes right.
// You are given an array of non-zero integers nums. The ant starts reading nums from the first element of it to its end.
// At each step, it moves according to the value of the current element: If nums[i] < 0, it moves left by -nums[i] units. If nums[i] > 0, it moves right by nums[i] units.
// Return the number of times the ant returns to the boundary.

class Solution {
    public int returnToBoundaryCount(int[] nums) {
        int x=0;
        int cnt=0;
        for(int n:nums){
            x+=n;
            if(x==0){
                cnt++;
            }
        }
        return cnt;
    }
}
```
</details>
