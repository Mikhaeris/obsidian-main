**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minTimeToType(string& word) {
        int curr = 'a';
        int time = 0;
        for (const char& ch : word) {
            int move = abs(ch - curr);
            time += min(move, 26 - move);
            ++time;
            curr = ch;
        }
        return time;
    }
};
```
**Explanation:**
	Цель: Есть специальное вводящее устройство в виде диска, в каждой ячейки находится буква. Требуется ввести слово, котрое дано. За одну еденицу времени можно повернуть круг на одну позицию или ввести букву на которую указывает вводяще устройство. Нужно узнать за какое минимальное время можно ввести эту строк.
	Pешение: Есть прямой ход и обратный. Прямой простое расстояние от текущей позиции до буквы или в другом направлении. Нужно выбрать минимальные путь и ввести эту букву.
