**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    vector<int> alph(26, 0);  
    string str = ""; cin >> str;  
    for (int i = 0; i < str.size(); ++i) {  
        alph[str[i] - 'a'] = 1;  
    }  
  
    int sum = 0;  
    for (int i = 0; i < alph.size(); ++i) {  
        sum += alph[i];  
    }  
  
    if (sum % 2) {  
        cout << "IGNORE HIM!" << endl;  
    }  
    else {  
        cout << "CHAT WITH HER!" << endl;  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Определать четность количества уникальных букв  в слове.
	Решение: Масссив из 26 элементов, где i-й элемент это буква в алфавите, если буква есть, то 1, если нет то 0. В конце подсчитать сумму всего массива - это и будет количестов различных символов в массиве. И вывести результат