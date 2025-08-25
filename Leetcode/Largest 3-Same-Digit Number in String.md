**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string largestGoodInteger(string num) {
	int count = 1, good_num = -1;
	for (int i = 1; i <= num.size(); i++) {
		if (num[i] != num[i-1]) {
			if (count >= 3) {
				good_num = max(num[i-1] - '0', good_num);
			}
			count = 0;
		}
		count++;
	}
	
	return (good_num != -1) ? string(3, good_num + '0') : "";
	}
};
```
**Explanation:**
	Цель: Дана строка цифр. Нужно найти макимальный подмассив размером три, в котором всы цифры равны.
	Решение: Проходится по каждому элементу и считать сколько раз подряд оно встречалось. Если количиство встереч больше или равно трем, значит это число подходит и нужно взять макимальное. В конце проверить, что такой подмассив вообще существует и вернуть его.
