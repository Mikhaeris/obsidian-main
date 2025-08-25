**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string first = "", second = "", ans = "";  
    cin >> first >> second;  
    for (int i = 0; i < first.size(); ++i) {  
        if (first[i] == second[i]) {  
            ans.push_back('0');  
        }  
        else {  
            ans.push_back('1');  
        }  
    }  
    cout << ans << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Даны две строки из нулей и едениц, нужно вернуть третью строку. Строки складываеются по правилу, если i-е элементы не равны, значит еденица, иначе ноль.
	Решение: За один цикл пройтись и вернуть строку.