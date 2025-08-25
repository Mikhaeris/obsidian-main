**Complexity:** Medium
Answer1:
	Time Complexity: O(N + M)
	Space Complexity: O(N/2)
Code:
Solution:
```cpp
class Solution {
public:
	int singleNumber(vector<int>& nums) {
        unordered_map<int,int> check_mp;
  
        for (const auto& num : nums) {
            ++check_mp[num];
        }
  
        for (const auto& pr : check_mp) {
            if (pr.second == 1) {
                return pr.first;
            }
        }
  
        return -1;
    }
};
```
**Explanation:**
	Цель: В массиве есть повтопяющиеся числа два раза, кроме одного, его нужно найти.
	Решение: Создать хэш таблицу [[Hash table]], где будет хранится числа и количество их повторений.
	Потом пройтись и вывести число(ключ), которое повторяется один раз.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int answer = 0;
        for (const auto& num : nums) {
            answer ^= num;
        }
  
        return answer;
    }
};
```
**Explanation:**
	Цель: В массиве есть повтопяющиеся числа два раза, кроме одного, его нужно найти.
	Решение: Применить свойство [[XOR]]. Одинаковые пары чисел сократятся, а единственный элемент останется в answer.
	Если чуть по другому, то можно сказать, что числа складываются, а если такое число уже было прибавлено, то оно убавится.