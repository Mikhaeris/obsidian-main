**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> getConcatenation(vector<int>& nums) {
        nums.resize(nums.size()*2); int k = 0;
        for (int i = nums.size()/2; i < nums.size(); ++i) {
            nums[i] = nums[k++];
        }
  
        return nums;
    }
};
```
**Explanation:**
	Цель: Дан массив, его надо удвоить(или сложить его два раза).
	Решение: Изменить размер исходного массива, умноженого на два, и заполнить оставшуюся часть. Вернуть данный массив.