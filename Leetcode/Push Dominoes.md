**Complexity:** Medium
**Task En:**
	There are `n` dominoes in a line, and we place each domino vertically upright. In the beginning, we simultaneously push some of the dominoes either to the left or to the right.
	After each second, each domino that is falling to the left pushes the adjacent domino on the left. Similarly, the dominoes falling to the right push their adjacent dominoes standing on the right.
	When a vertical domino has dominoes falling on it from both sides, it stays still due to the balance of the forces.
	For the purposes of this question, we will consider that a falling domino expends no additional force to a falling or already fallen domino.
	You are given a string `dominoes` representing the initial state where:
	`dominoes[i] = 'L'`, if the `ith` domino has been pushed to the left,
	`dominoes[i] = 'R'`, if the `ith` domino has been pushed to the right, and
	`dominoes[i] = '.'`, if the `ith` domino has not been pushed.
	Return _a string representing the final state_.
**Task Ru:** 
	В ряд выстроены `n` доминошек, и каждая из них изначально стоит вертикально. В начале мы одновременно толкаем некоторые доминошки либо влево, либо вправо.
	С каждой секундой каждая падающая влево доминошка толкает соседнюю слева. Аналогично, доминошки, падающие вправо, толкают соседние стоящие справа.
	Если вертикально стоящую доминошку одновременно толкают с обеих сторон, она остаётся на месте из-за баланса сил.
	Для целей этой задачи будем считать, что падающая доминошка не оказывает дополнительного воздействия на уже падающую или упавшую доминошку.
	Вам дана строка `dominoes`, представляющая начальное состояние, где:
	`dominoes[i] = 'L'`, если `i`-тая доминошка была толкнута влево,
	`dominoes[i] = 'R'`, если `i`-тая доминошка была толкнута вправо,
	`dominoes[i] = '.'`, если `i`-тая доминошка не была толкнута.
	Верните **строку, представляющую конечное состояние**.

**Example:**
	**Example 1:**
		**Input:** dominoes = "RR.L"
		**Output:** "RR.L"
		**Explanation:**
		The first domino expends no additional force on the second domino.
	**Example 2:**
		**Input:** dominoes = ".L.R...LR..L.."
		**Output:** "LL.RR.LLRRLL.."
**Constraints:**
	`n == dominoes.length`
	`1 <= n <= 105`
	`dominoes[i]` is either `'L'`, `'R'`, or `'.'`.
	
**Answer:**
	Resources:
		Time Complexity: O(n)
		Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    string pushDominoes(string dominoes) {
	    int first = 0, second = 0;
	    for (int i = 0, j = 0, k = 0; i < dominoes.size(); i++) {
	        if (dominoes[i] != '.') {
	            // if free L? like ...L
	            if (dominoes[i] == 'L') {
	                for (j = i - 1; j >= 0; j--) {
	                    if (dominoes[j] != '.')
	                        break;
	                    else
	                        dominoes[j] = 'L';
	                }
	            }
	            // get areas R...L
	            else if (dominoes[i] == 'R') {
	                // find symbol
	                for (j = i + 1; j < dominoes.size(); j++) {
	                    // if L, then process areas
	                    if (dominoes[j] == 'L') {
	                        first = i + 1, second = j - 1;
	                        while (first != second && (first - 1 != second)) {
	                            dominoes[first] = 'R';
	                            dominoes[second] = 'L';
	                            first++;
	                            second--;
	                        }
	                        i = j;
	                        break;
	                    }
	                    // if R, then i to j make R
	                    if (dominoes[j] == 'R') {
	                        for (k = i + 1; k < j; k++)
	                            dominoes[k] = 'R';
	                        break;
	                    }
	                    // check end str
	                    if (j == dominoes.size() - 1) {
	                        for (k = i + 1; k < dominoes.size(); k++)
	                            dominoes[k] = 'R';
	                        break;
	                    }
	                }
	            }
	        }
	    }
	    return dominoes;
	}
};
```

**Explanation:**
	Цель: Вывести результат падания доминошек
	Решение: Идея заключается в обработке окон(R....L).
		Искать символ, если 'L'
			Все доминошки слева от этого символа, если это '.' , переделывать в L
		если 'R'
			Искать какой-то символ справа
			если 'L'
				тогда два указателя, первый на начало окна и второй на конец окна
				Указатели, на своих позиция меняют точки на свое поадние(R или L), идут навстречу друг другу(первый++, второй--)
				если первый и второй указатель равны, то завершается(четное)
				если первый минус один равно второму, то завершается(нечетное)
			если 'R'
				тогда все доминошки до этой изменяются на R
			если до конца массива точки
				все изменяется на 'R'