**Complexity:** 800
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    set<int> st;  
  
    for (int i = 0; i < 3; ++i) {  
        int x = 0; cin >> x;  
        st.insert(x);  
    }  
  
    int f = *(++st.begin())- *st.begin();  
    int s = *(--st.end()) - *(++st.begin());  
    cout << f + s << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дано три числа - точки на плоскости. Нужно найти минимальное расстояние, чтобы три друга встретились в одной точке.
	Решение: Запихать эти числа в сет и из второго вычесть первое, из третьего вычесть второе и сложить - это минимальное расстояние.