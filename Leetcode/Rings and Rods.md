**Complexity:** Easy
Answer:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countPoints(string rings) {
        unordered_map<int, int> mp;

        for (int i = 0; i < rings.size(); i += 2) {
            int cur = mp[rings[i+1]];
            if (rings[i] == 'R') {
                cur |= 1 << 0;
            } else if (rings[i] == 'G') {
                cur |= 1 << 1;
            } else if (rings[i] == 'B') {
                cur |= 1 << 2;
            }
            mp[rings[i+1]] = cur;
        }

        int count = 0;
        for (const auto& pr : mp) {
            if (pr.second == 7) {
                ++count;
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Даны данные в которых говорится в каких стержнях находятся кольца с каким цветом. Нужно определить в скольких стержнях находятся кольца всех цветов.
	Pешение: Записать в хеш таблицу для каждого стрежня маску с цветам(где каждый бит означает нужный цвет). Если все три бита включены, то увеличивать счетчик.