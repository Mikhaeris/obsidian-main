**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
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
	Цель: Дан массив слов. Нужно узнать сколько слов на отрезе от l до r начинаюся с главной и заканчиваются гласной.
	Решение: Проходится от l до r и проверять первыую и полсдежнюю букву слова.