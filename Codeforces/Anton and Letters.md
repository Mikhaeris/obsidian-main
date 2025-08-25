**Complexity:** 800
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    unordered_set<char> st;  
  
    for (int c; (c = getchar()) != '\n'; ) {  
        if (c >= 'a' && c <= 'z') {  
            st.insert(c);  
        }  
    }  
  
    cout << st.size() << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дана строка букв через запятые, обернутые в фигурные кавычки. Нужно посчитать количество уникальных букв.
	Решение: Считывать строку посимвольно и если это буква, то добавлять в сет.