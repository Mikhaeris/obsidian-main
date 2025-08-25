**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string addBinary(string a, string b) {
		string ans;
		  
		int carry = 0;
		int i = a.size()-1, j = b.size()-1;
		while (i >= 0 || j >= 0 || carry) {
			if (i >= 0) {
				carry += a[i--] - '0';
			}
			if (j >= 0) {
				carry += b[j--] - '0';
			}
			ans += carry % 2 + '0';
			carry /= 2;
		}
		  
		int l = 0, r = ans.size()-1;
		while (l < r) {
			int temp = ans[l];
			ans[l++] = ans[r];
			ans[r--] = temp;
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Даны две строки, представляющие собой двоичные числа, нужно сложить в двоичной системе и вывести эти два числа.
	Решение: Проходимся одновременно во двум строкам с конца. В carry накапливаем сумму. В конец строки прибавляем остаток деления суммы от двух( 0 % 2 = 0; 1 % 2 = 1; 2 % 2 = 0; 3 % 2 = 1). Значит в carry надо сохранить деленное на 2. И так проходится пока не закончится первая строка, вторая или carry.
	В конце нужно перевернуть строку и вернуть результат.