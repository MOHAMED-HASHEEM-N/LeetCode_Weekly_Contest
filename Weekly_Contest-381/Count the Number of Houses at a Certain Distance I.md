## 3015. Count the Number of Houses at a Certain Distance I

<details>
<summary>Java</summary>

```java

// You are given three positive integers n, x, and y.
// In a city, there exist houses numbered 1 to n connected by n streets. There is a street connecting the house numbered i with the house numbered i + 1 for all 1 <= i <= n - 1 . An additional street connects the house numbered x with the house numbered y.
// For each k, such that 1 <= k <= n, you need to find the number of pairs of houses (house1, house2) such that the minimum number of streets that need to be traveled to reach house2 from house1 is k.
// Return a 1-indexed array result of length n where result[k] represents the total number of pairs of houses such that the minimum streets required to reach one house from the other is k. Note that x and y can be equal.


class Solution {
    public int[] countOfPairs(int n, int x, int y) {
        int[] res=new int[n];
        for(int i=1;i<=n;i++){
            for(int j=i+1;j<=n;j++){
                int d1=Math.abs(i-j);
                int d2=Math.abs(i-x)+Math.abs(j-y)+1;
                int d3=Math.abs(i-y)+Math.abs(j-x)+1;
                int min=Math.min(d1,Math.min(d2,d3));
                res[min-1]++;
            }
        }
        for(int i=0;i<n;i++){
            res[i]=res[i]*2;
        }
        return res;
    }
}
```
</details>
