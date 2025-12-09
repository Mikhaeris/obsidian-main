**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> findPeaks(vector<int>& mountain) {
        int n = mountain.size();
        vector<int> vec;
        for (int i = 1; i < n-1; ++i) {
            if (mountain[i-1] < mountain[i] && mountain[i] > mountain[i+1]) {
                vec.push_back(i);
            }
        }
        return vec;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно найти все пики. Первый и последний элементы не явля.тся пиками.
	Решение: Проверять каждый индекс на пик.