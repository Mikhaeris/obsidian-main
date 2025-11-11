**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class NumArray {
public:
    NumArray(vector<int>& nums) : prefsum_(nums) {
        for (int i = 1; i < nums.size(); ++i) {
            prefsum_[i] += prefsum_[i-1];
        }
    }
    
    int sumRange(int left, int right) {
        if (left == 0) {
            return prefsum_[right];
        }
        return prefsum_[right] - prefsum_[left - 1];
    }
private:
    vector<int> prefsum_;
};
```
**Explanation:**
	Цель: Нужно реализовать массив, который предоставляется доступ к сумме чисел по диапозону.
	Решение: С помощью префикссуммы посчитать сумму элементов до, т.е. кажды элемент содержится сумму элементов от 0 до него(включая). Значит чтобы получить сумму чисел от левого идекса, нужно вычесть из правого индекса сумму чисел до левого индекса. Т.е. индекс до сожердит сумму чисел до 