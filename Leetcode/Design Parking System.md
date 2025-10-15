**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class ParkingSystem {
public:
    ParkingSystem(int big, int medium, int small) {
        slots.resize(3);
        slots[0] = big;
        slots[1] = medium;
        slots[2] = small;
    }
    
    bool addCar(int c) {
        if (slots[c-1] > 0) {
            slots[c-1]--;
            return true;
        }
        return false;
    }

private:
    vector<int> slots;
};
```
**Explanation:**
	Цель: Создать систему парковки, где есть места и машины типов 1, 2, 3.
	Pешение: Массив из количества мест. При добавлении машины, проверить есть ли места и уменьшать количество мест, иначе вернуть что мест нет.