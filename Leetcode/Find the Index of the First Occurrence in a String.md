**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int strStr(string haystack, string needle) {  
	    int think = 0; bool flag = false;  
	    for (int i = 0, j = 0; i < haystack.size() && j < needle.size(); i++) {  
	        if (haystack[i] == needle[j]) {  
	            if (j == 0) {  
	                think = i;  
	            }  
	            j++;  
	            flag = true;  
	        }  
	        else {  
	            j = 0;  
	            if (flag) {  
	                i = think;  
	            }  
	            flag = false;  
	        }  
	  
	        if (j == needle.size()) {  
	            return think;  
	        }  
	    }  
	  
	    return -1;  
	}
};
```
**Explanation:**
	Цель: Дана строка и слово. Нужно проверить, содержится ли это слово в этой строке.
	Решение: На самом деле простая проверка по символьно, если слово не подходит, тогда указатель возвращается в начало этой предполагаемой подстроки плюс один.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int strStr(string haystack, string needle) {
        for (int i = 0; i <= haystack.length() - needle.length(); ++i) {
            if (haystack.substr(i, needle.length()) == needle) {
                return i;
            }
        }
        return -1;
    }
};
```
**Explanation:**
	Цель: Дана строка и слово. Нужно проверить, содержится ли это слово в этой строке.
	Решение: Тоже саамое что и в прошлом, только с помощью встроенных функций у класса string.