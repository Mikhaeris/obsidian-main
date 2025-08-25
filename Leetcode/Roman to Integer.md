**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int romanToInt(string s) {
        unordered_map<char, int> numTransformation =
        {{'I', 1},
        {'V', 5},
        {'X', 10},
        {'L', 50},
        {'C', 100},
        {'D', 500},
        {'M', 1000}};
        
        int answer = 0;
        for (int i = 0; i < s.length()-1; ++i) {
            if (numTransformation[s[i]] < numTransformation[s[i+1]]) {
                answer -= numTransformation[s[i]];
            }
            else {
                answer += numTransformation[s[i]];
            }
        }
        
        return answer + numTransformation[s[s.length()-1]];
    }
};
```
**Explanation:**
	Цель: Нужно перевести число из римской системы счисления в арабскую
	Решение: Создать хэш-таблицу, где каждой римской цифрой соответсвует арабская.
	Проходится по каждой цифре до размера минус один.
	Если следующая цифра больше текущей, то нужно вычести эту цифру из ответа.
	Иначе прибавить к ответу данную цифру.
	В конце к ответу добавить последнюю цифру.