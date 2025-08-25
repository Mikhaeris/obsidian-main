**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    for (int i = 0; i < n; ++i) {  
        vector<int> vec(3);  
        cin >> vec[0] >> vec[1] >> vec[2];  
        sort(vec.begin(), vec.end());  
        if (vec[0] + vec[1] == vec[2]) {  
            cout << "YES" << endl;  
        }  
        else {  
            cout << "NO" << endl;  
        }  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Проверить, есть ли такие два числа, которые при сложении дадут третье.
	Решение: Записать в массив и отсортировать его. Проверить сумма двх первых чисел равняется третьему и вывести ответ.