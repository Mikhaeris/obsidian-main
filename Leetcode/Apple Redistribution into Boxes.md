**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
    int minimumBoxes(vector<int>& apple, vector<int>& capacity) {
        int suma = 0;
        for (const auto& a : apple) {
            suma += a;
        }

        sort(capacity.begin(), capacity.end(), [](int& a, int& b){ return a > b; });

        int count = 0;
        int sumb = 0;
        for (const auto& c : capacity) {
            sumb += c;
            ++count;
            if (sumb >= suma) {
                break;
            }
        }

        return count;
    }
```
**Explanation:**
	Цель: Дано пакеты с яблоками и коробки. Нужно узнать какой минимальное количество коробок потребуется чтобы переестить все яблоки из пакетов в коробоки.
	Pешение: Посчитать сколько всего яблок. Отсортировать коробоки по убыванию и смотреть когда не останется яблок. Вернуть колчеиство коробок.