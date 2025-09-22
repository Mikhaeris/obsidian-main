**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution1:
```cpp
class Solution {
public:
	string winningPlayer(int x, int y) {
		bool turn = false;
		while (x >= 1 && y >= 4) {
			x -= 1;
			y -= 4;
			turn = !turn;
		}
		return (turn) ? "Alice" : "Bob";
	}
};
```
**Explanation:**
	Цель: Узнать кто победит в игре. Если за ход нужно взять из кучек 115 моент в первой кучке моенты номиналом 75, в  второй 10.
	Решение: Тривиальным алгоритмом узнать кто это.
	
Solution2:
```cpp
class Solution {
public:
	string winningPlayer(int x, int y) {
		int turn = min(x, y / 4);
		return (turn & 1) ? "Alice" : "Bob";
	}
};
```
**Explanation:**
	Цель: Узнать кто победит в игре. Если за ход нужно взять из кучек 115 моент в первой кучке моенты номиналом 75, в  второй 10.
	Решение: Проиграет первый тот, кто не сможет взять из какой-либо кучки. Проверить чей это будет ход(четный или нечетный ход). Вернуть ответ.