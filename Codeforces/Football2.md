**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    string s1 = "", s2 = "";  
    int g1 = 0, g2 = 0;  
    for (int i = 0; i < n; ++i) {  
        string s = ""; cin >> s;  
        if (s1.size() == 0) {  
            s1 = s;  
        }  
        else if (s2.size() == 0 && s != s1) {  
            s2 = s;  
        }  
  
        if (s == s1) {  
            ++g1;  
        }  
        else {  
            ++g2;  
        }  
    }  
  
    if (g1 > g2) {  
        cout << s1 << endl;  
    }  
    else {  
        cout << s2 << endl;  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дан список названия команд, когда упоминается комадна - значит она забила гол. Нужно узнать какая команда победила и вывести ее название.
	Решение: Сначала нужно понять какая команда ке является и первое условие заполняет команды. Потом идет заполнение количества голов. Вывести победившую команду.