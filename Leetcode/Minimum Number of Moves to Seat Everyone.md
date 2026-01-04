**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minMovesToSeat(vector<int>& seats, vector<int>& students) {
        sort(seats.begin(), seats.end());
        sort(students.begin(), students.end());

        int moves = 0;
        for (int i = 0; i < seats.size(); ++i) {
            moves += abs(seats[i] - students[i]);
        }
        return moves;
    }
};
```
**Explanation:**
	Цель: Дана плоскость, на которой стоят стулья и студенты. Нужно узнать какое минимальное количество шагов потребуется чтобы все студенты сели.
	Pешение: Отсортировать массивы(т.к. количество студентов равнеяет количеству мест) таким образом каждый студент найдет самый близкий к нему стул. Пройтись по всем тульям и найти расстояние по модулю для каждого студента.