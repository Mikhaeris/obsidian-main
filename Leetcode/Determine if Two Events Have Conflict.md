**Complexity:** Easy
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool haveConflict(vector<string>& event1, vector<string>& event2) {
		return event1[0] <= event2[1] && event1[1] >= event2[0];
	}
};
```
**Explanation:**
	Цель: Дано начало и конец двух событий. Узнать пересекуются ли они.
	Решение: Проверить, что конец второго события больше начала первого события и конец первого события больше начала второго.
		1----------6
			3-------------9