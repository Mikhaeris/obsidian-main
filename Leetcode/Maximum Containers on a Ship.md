**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	int maxContainers(int n, int w, int maxWeight) {
		int area = n * n;
		int maxContainers = maxWeight / w;
		  
		if (area > maxContainers) {
			return maxContainers;
		}
		  
		return area;
	}
};
```
**Explanation:**
	Цель: Дана сторона коробля, вес одного груза и макимальная грузоподъемность коробля. Нужно узнать какое максиаьное количество контейнеров можнго погрузить на корабль
	Решение: Узнать сколько всего можно положить контейнеров на корабль, максимальное количество контейнеров учитывая грузоподъемность. Если количество контейнеров больше максимального количество контейнеров учитывая грузоподъемность, то вернуть второе, иначе первое.