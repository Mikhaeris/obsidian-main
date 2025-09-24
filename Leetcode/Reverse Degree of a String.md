**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(?)
Code:
Solution:
```cpp
class Solution {
public:
	int reverseDegree(string s) {
	int sum = 0;
	for (int i = 0; i < s.length(); ++i) {
	sum += (26 - (s[i] - 'a')) * (i + 1);
	}
	return sum;
	}
};
```
**Explanation:**
	Цель: Даны две строки, в которых через точки стоят числа, нужно сравнить эти числа. Если строки не равны, то меньшая дополняется нулями.
	Pешение: Расспарсить числа в массив, дополнить нулями меньший массив. Сранвить каждый элемент в массиве.