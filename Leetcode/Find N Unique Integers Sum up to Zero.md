**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> sumZero(int n) {
		vector<int> vec(n);
		  
		if (n % 2) {
			vec[--n] = 0;
		}
		
		for (int i = 0, num = 1; i < n; ++i) {
			if (i % 2 == 0) {
				vec[i] = num;
			} else {
				vec[i] = -num;
				++num;
			}
		}
		  
		return vec;
	}
};
```
**Explanation:**
	Цель: Дано число, нужно создать вернуть такой массив, что сумма элементов в нем равняется 0 и элементы не повторяются.
	Решение: Заполнять элементы от 1 до n/2, чтобы сначала было 1, затем -1, 2, -2 и т.д. Если даннное число нечетное, то последним элементом сделать нолик. Вернуть данный массив.