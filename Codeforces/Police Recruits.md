**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int curr_pol = 0, count_crimes = 0;  
    for (int i = 0; i < n; ++i) {  
        int new_n = 0; cin >> new_n;  
        if (new_n > 0) {  
            curr_pol += new_n;  
        }  
        else {  
            if (curr_pol == 0) {  
                ++count_crimes;  
            }  
            else {  
                --curr_pol;  
            }  
        }  
    }  
  
    cout << count_crimes << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать скольок преступленйи будет совершено. Если число больше 0 - знаичт пришли новые полицейские, если меньше, значит совершилось преступление. Полецейский расследует дело, если все полицейские заняты - знаичт преступление не раскрыто.
	Решение: Две переменные - количество свободных полицейских и количество не раскрытых реступлений, заполнять их по условияю и вывести ответ.