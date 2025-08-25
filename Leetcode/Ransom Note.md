**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)?
Code:
Solution:
```cpp
class Solution {
public:
	bool canConstruct(string ransomNote, string magazine) {
		array<int, 26> arr;
		arr.fill(0);
		
		for (const auto& ch : magazine) {
			++arr[ch - 'a'];
		}
		  
		for (const auto& ch : ransomNote) {
			if (--arr[ch - 'a'] < 0) {
				return false;
			}
		}
		  
		return true;
	}
};
```
**Explanation:**
	Цель: Проверить, содержатся ли все символы из первой строки во второй.
	Решение: Подсчитать количество символов второй строки в массив. Вторым проходом вычитать символы первой строки из второй, если количество будет меньше нуля - знаичт не подходит.