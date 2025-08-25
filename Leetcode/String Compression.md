**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int compress(vector<char>& chars) {
        for (int i = 0; i < chars.size()-1; ++i) {
            if (chars[i] == chars[i + 1]) {
  
                int count_repeat = 1;
                while (i < chars.size() - 1 && chars[i] == chars[i + 1]) {
                    ++count_repeat;
                    chars.erase(chars.begin() + i+1);
                }
  
                if (count_repeat > 9) {
                    int offset = 0;
                    while (count_repeat) {
                        chars.insert(chars.begin() + i + 1, count_repeat % 10 + '0');
                        count_repeat /= 10;
                        ++offset;
                    }
                    i += offset;
                }
                else {
                    chars.insert(chars.begin() + i + 1, count_repeat + '0');
                    ++i;
                }
            }
        }
  
        return chars.size();
    }
};
```
**Explanation:**
	Цель: Сжать строку, добаваляя после сивола количество повторений.
	Решение: Проходится по каждому символу,
	Если сивол равен следующему, то считать количество повторений, удаляя повторяющийся символ.
	Если число повторений больше 9, то добавлять по разрядам.
	Иначе просто добавить цифру.
	Вернуть размер массива.