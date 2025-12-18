**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool hasAlternatingBits(int n) {
        int last = (n & 1) ? 1 : 0;
        
        while (n) {
            n >>= 1;
            int bit = n & 1;
            if (bit == last) {
                return false;
            }
            last = bit;
        }
        
        return true;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно проверить, что все биты в нем чередуются.
	Pешение: Пройтись по всем битам, запоминая последний и сравнить текущей и предыдущий. Если они равны то вернуть false, иначе true.