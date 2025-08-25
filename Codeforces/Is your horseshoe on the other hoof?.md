**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    set<int> st;  
    for (int i = 0; i < 4; ++i) {  
        int n = 0; cin >> n;  
        st.insert(n);  
    }  
  
    cout << 4 - st.size() << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать сколько чисел надо заменить, чтобы все числа были неповторяющиеся.
	Решение: Запихивать числа в сет и потом 4 - размер сета.