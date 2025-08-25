**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0, k = 0; cin >> n >> k;  
    vector<int> vec(n);  
    --k;  
    for (int i = 0; i < vec.size(); ++i) {  
        cin >> vec[i];  
    }  
  
    int ans = 0;  
    for (int i = 0; i < n; ++i) {  
        if (vec[i] > 0 && vec[i] >= vec[k]) {  
            ++ans;  
        }  
    }  
  
    cout << ans << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно узнать сколько учатников пройдет в следующий раунд по следующему правилу, i-й участник должен быть больше или равен k-ому участнику.
	Решение: Записать всех участников в вектор. Дальше проходится по вектору и проверять условие.