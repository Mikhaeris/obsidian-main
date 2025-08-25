**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int findLucky(vector<int>& arr) {  
	    unordered_map<int, int> map;  
	    for (const auto& num : arr) {  
	        map[num]++;  
	    }  
	  
	    for (const auto& pair : map) {  
	        if (pair.first == pair.second) {  
	            return pair.first;  
	        }  
	    }  
	  
	    return -1;  
	}
};
```
**Explanation:**
	Цель: Счастливое число в массиве - это такое число, которое встречается столько раз, сколько его значение.
	Решение: Создать хеш-таблицу [[Hash table]], в которой ключ - число, значение - сколько раз оно встречается в массиве. Потом пройтись и найти максимальное число. 

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int findLucky(vector<int>& arr) {

	}
};
```
**Explanation:**
	Цель: Счастливое число в массиве - это такое число, которое встречается столько раз, сколько его значение.
	Решение: Отсортировать массив и проходиться по элементам, параллельно считая сколько раз оно встречается. Вывести максимальное.