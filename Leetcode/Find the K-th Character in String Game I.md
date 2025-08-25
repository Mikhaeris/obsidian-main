**Complexity:** Easy
Answer1:
	Time Complexity: O(K)
	Space Complexity: O(K)
Code:
Solution:
```cpp
class Solution {
public:
	char kthCharacter(int k) {  
	    string s = "a";  
	    while (s.size() < k) {  
	        string ns;  
	        for (int i = 0; i < s.size(); i++) {  
	            if (s[i] + 1 > 'z') {  
	                 ns.push_back('a');  
	            }  
	            else {  
	                ns.push_back(s[i]+1);  
	            }  
	        }  
	        s += ns;  
	    }  
	    return s[k-1];  
	}
};
```
**Explanation:**
	Цель: Дан символ 'a', за один ход все символы в строке сдвигаются на право на один и добавляются к изначальной строке. Нужно найти k символы.
	Решение: Выполнять эти действия пока не будет найден k-ый символ.

Answer2:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	char kthCharacter(int k) {
		return __builtin_popcount(k-1) + 'a';
	}
};
```
**Explanation:**
	Цель: Дан символ 'a', за один ход все символы в строке сдвигаются на право на один и добавляются к изначальной строке. Нужно найти k символы.
	Решение: Математика. Посчитать сколько едениц в числе k-1 и прибавить их к 'a'. Есть доказательство, но я не до конца понял как это работает. Но суть такая, что каждый раз когда мы добвляем символы, то мы сдвигаем их вправо на один, значит всего смещений будет k-1. Отсюда следует (так как оно растет в каждый раз в два), что для этйо последовательности kсимвол и будет количество едениц в k-1 + 'a'.