**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    int n = 0, t = 0; cin >> n >> t;  
  
    vector<char> vec(n);  
    for (auto& p : vec) {  
        cin >> p;  
    }  
  
    for (int i = 0; i < t; ++i) {  
        for (int j = 1; j < n; ++j) {  
            if (vec[j-1] == 'B' && vec[j] == 'G') {  
                swap(vec[j-1], vec[j]);  
                ++j;  
            }  
        }  
    }  
  
    for (const auto& p : vec) {  
        cout << p;  
    }  
    cout << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дана очередь, за одну секунду B и G могут меняться местми, как быдет выглядеть очередь через t секунд?
	Решение: Самый примитивный алгоритм, каждую секунду менять позиции во всех доступных позициях, вернуть массив.