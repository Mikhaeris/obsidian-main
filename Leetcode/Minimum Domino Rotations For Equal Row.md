**Complexity:** Medium
**Task:**
	En: In a row of dominoes, `tops[i]` and `bottoms[i]` represent the top and bottom halves of the `ith` domino. (A domino is a tile with two numbers from 1 to 6 - one on each half of the tile.)
	We may rotate the `ith` domino, so that `tops[i]` and `bottoms[i]` swap values.
	Return the minimum number of rotations so that all the values in `tops` are the same, or all the values in `bottoms` are the same.
	If it cannot be done, return `-1`.
	Ru: В ряду домино `tops[i]` и `bottoms[i]` представляют верхнюю и нижнюю половины _i_-й фишки домино. (Фишка домино — это плитка с двумя числами от 1 до 6 — по одному на каждой половине.)
	Мы можем поворачивать _i_-ю фишку домино, меняя местами значения `tops[i]` и `bottoms[i]`.
	Верните **минимальное количество поворотов**, чтобы **все значения в массиве `tops` стали одинаковыми** или **все значения в массиве `bottoms` стали одинаковыми**.
	Если это невозможно — верните **-1**.
	
**Example:**
	**Example 1:**
		**Input:** tops = [2,1,2,4,2,2], bottoms = [5,2,6,2,3,2]
		**Output:** 2
		**Explanation:**
		The first figure represents the dominoes as given by tops and bottoms: before we do any rotations.
		If we rotate the second and fourth dominoes, we can make every value in the top row equal to 2, as indicated by the second figure.
	**Example 2:**
		**Input:** tops = [3,5,1,2,3], bottoms = [3,6,3,3,4]
		**Output:** -1
		**Explanation:**
		In this case, it is not possible to rotate the dominoes to make one row of values equal.
**Constraints:**
	`2 <= tops.length <= 2 * 104`
	`bottoms.length == tops.length`
	`1 <= tops[i], bottoms[i] <= 6`
	
Answer:
	Time Complexity: Best - O(n), Worst - O(2n)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int minDominoRotations(vector<int>& tops, vector<int>& bottoms) {
        int size = tops.size();
        int currentDigitTops = 0, currentDigitBottoms = 0;
        if (tops[0] == tops[1] || tops[0] == bottoms[1]) {
            currentDigitTops = tops[0];
        if (bottoms[0] == tops[1] || bottoms[0] == bottoms[1]) {
            currentDigitBottoms = bottoms[0];
        if (currentDigitTops == 0 && currentDigitBottoms == 0) {
            return -1;
        
        int currentDigit = 0;
        if (currentDigitTops != 0 && currentDigitBottoms != 0 && currentDigitTops != currentDigitBottoms) {
            if (size == 2)
                return 1;
            for (int i = 0; i < size; i++) {
                if (tops[i] != currentDigitTops && bottoms[i] != currentDigitTops) {
                    currentDigit = currentDigitBottoms;
                    break;
                }
                else if (tops[i] != currentDigitBottoms && bottoms[i] != currentDigitBottoms) {
                    currentDigit = currentDigitTops;
                    break;
                }
            }
        }
        else {
            currentDigit = currentDigitTops != 0 ? currentDigitTops : currentDigitBottoms;
        }
        
        int countDigitTops = 0, countDigitBottom = 0;
        for (int i = 0; i < size; i++) {
            if (tops[i] == currentDigit)
                countDigitTops++;
            if (bottoms[i] == currentDigit)
                countDigitBottom++;
            if (tops[i] != currentDigit && bottoms[i] != currentDigit)
                return -1;
        }
        return (countDigitTops > countDigitBottom) ? (size - countDigitTops) : (size - countDigitBottom);

    }
};
```

**Explanation:**
	Проверка на наличие повторяющихся чисел в первых двух доминошка.
	Если повторяющихся нет - вернуть -1, если потовторяющихся два, тогда
		проходится по каждой доминошке и проверять, если в данной доминошке, нет одно из двух цифр(на первом шаге берутся две цифры, если их две), то другая становится главной.
	Проходится по каждой доминошке и считать количество повторений сверху и снизу.
	Если в доминошке цифра не встречается - возвращать -1.
	Теперь гарантируется что сверху и снизу это число имеется и нет дырок. Значит, зная количество повторений сверху и снизу, можно посчитать сколько доминошек нужно перевернуть. Если сверху доминошек больше - из всего количество доминошек вычесть количество доминошек сверху, если снизу доминошек больше - из всего количество доминошек вычесть количество доминошек снизу.