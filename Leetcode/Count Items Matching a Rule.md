**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countMatches(vector<vector<string>>& items, string ruleKey, string ruleValue) {
        int n = items.size();

        int key = 0;
        if (ruleKey == "type") { key = 0; }
        else if (ruleKey == "color") { key = 1; }
        else if (ruleKey == "name") { key = 2; }

        int count = 0;
        for (int i = 0; i < n; ++i) {
            if (items[i][key] == ruleValue) {
                ++count;
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Дан список предметов(тип;цвет;имя), даны правила(ключ;значение). Нужно посчитать сколько предметов соответсвует данному правилу.
	Pешение: Проверить все предметы по этим паравилам и вывести их количество.