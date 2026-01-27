**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int max_volume = 0;
  
        int left = 0, right = height.size()-1;
        while (left < right) {
            max_volume = max(min(height[left], height[right]) * (right - left), max_volume);
  
            if (height[left] < height[right]) {
                ++left;
            }
            else {
                --right;
            }
        }
  
        return max_volume;
    }
};
```
**Explanation:**
	Цель: Вычислить максимальный объем между столбцами.
	Решение: Два указател. Один слева, другой справа. Каждый раз считать объем между двумя указателями.
	Стараться чтобы не указатели был максимальный длины столбец.
	Т.е. если левый столбец меньше правого, то двигать левый и наоборот.