**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    vector<int> vec(n);  
  
    int p = 0; cin >> p;  
    for (int i = 0; i < p; ++i) {  
        int inp = 0; cin >> inp;  
        ++vec[inp-1];  
    }  
  
    int q = 0; cin >> q;  
    for (int i = 0; i < q; ++i) {  
        int inp = 0; cin >> inp;  
        ++vec[inp-1];  
    }  
  
    for (int i = 0; i < vec.size(); ++i) {  
        if (vec[i] == 0) {  
            cout << "Oh, my keyboard! " << endl;  
            return 0;  
        }  
    }  
  
    cout << "I become the guy. " << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно проверить, могут ли ребята вдвоем пройти игру.
	Решение: Просто проверка.