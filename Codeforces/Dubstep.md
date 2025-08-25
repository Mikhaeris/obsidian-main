**Complexity:** 900
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    string s = ""; cin >> s;  
  
    string answer = "";  
    bool flag = false;  
    for (int i = 0; i < s.size();) {  
        if (s.substr(i, 3) != "WUB") {  
            answer.push_back(s[i]);  
            ++i;  
            flag = true;  
        }  
        else {  
            if (flag) {  
                answer.push_back(' ');  
                flag = false;  
            }  
            i += 3;  
        }  
    }  
  
    cout << answer << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Была строка, между слова стоят слова WUB, нужно вернуть исходную строку.
	Решение: Идея просто скипать последовательность WUB и с помощью флага отслуживать конец слова и потом вывести найденную строку.