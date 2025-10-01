**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int triangularSum(vector<int>& nums) {
        if (nums.size() == 1) {
            return nums[0];
        }
        for (int i = nums.size()-1; i > 0; --i) {
            for (int j = 0; j < i; ++j) {
                nums[j] = (nums[j] + nums[j+1]) % 10;
            }
        }
        return nums[0];
    }
};
```
**Explanation:**
	Цель: Нужно найти сумму массив трегольным способом. Каждый элемент равен сумме текщего плюс следующего, так пока не останется один элемент.
	Pешение: Проходится пока размер массива не станет еденице. Складывать текущей и следеющий элемент взяв остаток от десяти записать в текушую позицию.