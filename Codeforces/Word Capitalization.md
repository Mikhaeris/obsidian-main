**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string str = ""; cin >> str;  
    if (str[0] > 96 && str[0] < 123) {  
        str[0] = str[0] - 32;  
    }  
    cout << str << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Сделать первую букву заглавной.
	Решение: Если первая буква находится в диапазоне от 95 до 123, то она маленькая и нужно сметь ее на 32 символа назад.