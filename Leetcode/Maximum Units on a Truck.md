**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maximumUnits(vector<vector<int>>& boxTypes, int truckSize) {
        sort(boxTypes.begin(), boxTypes.end(),
            [](const auto& a, const auto& b) {
                return a[1] > b[1];
            });

        int units = 0;
        for (const auto& box : boxTypes) {
            if (truckSize == 0) {
                break;
            }

            int take = min(truckSize, box[0]);
            units += take * box[1];
            truckSize -= take;
        }

        return units;
    }
};
```
**Explanation:**
	Цель: Даны разные типы коробок, в котрых хранятся разное количество чего-то и дана вместимость грузовика. Требуется взять такие коробки, которые дадут макисомальное количесвто едениц чего-то.
	Pешение: Отсортировать коробки по количеству в них чего-то. Пройтись по массиву и брать первые коробоки, если в грузовике не хватате места, то взять только часть корбок.