**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    int answer = 0;  
    for (int i = 0; i < n; ++i) {  
        int certainty = 0; int inp = 0;  
        for (int j = 0; j < 3; ++j) {  
            cin >> inp;  
            certainty += inp;  
        }  
  
        if (certainty > 1) {  
            ++answer;  
        }  
    }  
  
    cout << answer << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно посчитать, в скольких строчках сумма цифр больше или равно 2.
	Решение: Если в строчке сумма боьше или равно 2, то прибалять к ответу плюс 1. Вывести ответ.