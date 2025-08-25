**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<vector<int>> generate(int numRows) {
		vector<vector<int>> triangle(numRows);
		  
		for (int i = 0; i < numRows; ++i) {
			triangle[i] = vector<int>(i+1, 1);
			  
			for (int j = 1; j < i; ++j) {
				triangle[i][j] = triangle[i-1][j-1] + triangle[i-1][j];
			}
		}
		  
		return move(triangle);
	}
};
```
**Explanation:**
	Цель: Нужно вывести n рядов треугольника Паскля.
	Решение: Создать вектор векторов на n векторов. Дальше каждой итерацией заполнять i-ый вектор - вектором размером i+1(так как начинается итерация по циклу с нуля) и заполнять его еденичками(так как первый и последний элемент всегда еденички). Заполнять этот ряд, где каждый элемент равняется сумме элеентов выше(правого и левого). Вернуть получившийся треугольник.
