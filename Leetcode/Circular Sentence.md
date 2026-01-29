**Complexity:** Easy  
Answer:  
- Time Complexity: O(N)
- Space Complexity: O(N)

Code:  
```cpp
class Solution {
public:
    bool isCircularSentence(string str) {
        if (str[0] != str[str.size()-1]) {
            return false;
        }

        for (int i = 0; i < str.size(); ++i) {
            if ((str[i] == ' ') && (str[i-1] != str[i+1])) {
                return false;
            }
        }

        return true;
    }
};
```
**Explanation:**
- Цель: Дана строка, нужно проверить что она является зацикленной. Зацикленная строка, это такая строка, в которой последняя буква слова равняется первой букве следующего слова.
- Pешение: Проверить первое и последнее слово. Дальше искать пробелы и 