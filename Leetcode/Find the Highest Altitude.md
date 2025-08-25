**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int largestAltitude(vector<int>& gain) {
        int max_height = 0, current_height = 0;
        for (int i = 0; i < gain.size(); ++i) {
            current_height += gain[i];
  
            if (max_height < current_height) {
                max_height = current_height;
            }
        }
  
        return max_height;
    }
};
```
**Explanation:**
	Цель: Дан путь с изменением высоты, нужнос найти максимально высокую точку на пути.
	Решение: Проходится по каждому элементу массива и прибавлять к данной высоте.
	Срванивать с максимальной и в конце возвращать максимальнудю высоту.