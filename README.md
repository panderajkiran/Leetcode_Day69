# Leetcode_Day69
## Day 69 – LeetCode 118: Pascal's Triangle

**Problem:** [Pascal's Triangle](https://leetcode.com/problems/pascals-triangle/)  
**Difficulty:** Easy  
**Language:** Java  
**Topics:** Arrays, ArrayList, Dynamic Programming

### Approach
- Create a list to store all rows of Pascal's Triangle.
- Iterate through each row from `0` to `numRows - 1`.
- Add `1` at the beginning and end of every row.
- For the middle elements, calculate the sum of the two elements directly above them from the previous row.
- Add each completed row to the result and return the final list.

### Java Solution
```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<>();

        for (int i = 0; i < numRows; i++) {
            List<Integer> row = new ArrayList<>();

            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    row.add(1);
                } else {
                    row.add(result.get(i - 1).get(j - 1)
                        + result.get(i - 1).get(j));
                }
            }

            result.add(row);
        }

        return result;
    }
}

Complexity Analysis
- Time Complexity: O(n²)
- Space Complexity: O(n²)
Here, n represents the number of rows.
Key Learning
Pascal's Triangle demonstrates how each row can be constructed using values from the previous row. It helped me practice nested loops, 2D ArrayLists, and building solutions step by step.
Day 69/100 — Learning consistently, one problem at a time! 🚀
#LeetCode #Java #DSA #ProblemSolving #100DaysOfCode
