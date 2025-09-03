**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int countSeniors(vector<string>& details) {
		int count = 0;
		for (const auto& pas : details) {
			count += ((pas[11]-'0')*10+(pas[12]-'0')) > 60;
		}
		return count;
	}
};
```
**Explanation:**
	Цель: Дана строка с детялами о пассажире длинной 15 символов. Первые 10 - номер телефона, следующий пол, следующие два возраст и полсдение два - место. Нужно узнать сколько пассажиров старше 60 лет.
	Решение: Взять 11 и 12 индекс и превратить их в число, сравнить с 60 и прибавить в ответ. Вернуть количество.