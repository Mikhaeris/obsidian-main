**Complexity:** Medium
**Task:**
	En: Given a list of `dominoes`, `dominoes[i] = [a, b]` is **equivalent to** `dominoes[j] = [c, d]` if and only if either (`a == c` and `b == d`), or (`a == d` and `b == c`) - that is, one domino can be rotated to be equal to another domino.
	Return _the number of pairs_ `(i, j)` _for which_ `0 <= i < j < dominoes.length`_, and_ `dominoes[i]` _is **equivalent to**_ `dominoes[j]`.
	Ru: Дан список домино, где `dominoes[i] = [a, b]` считается **эквивалентным** `dominoes[j] = [c, d]`, если и только если выполняется одно из двух условий: либо (`a == c` и `b == d`), либо (`a == d` и `b == c`) — то есть одно домино можно повернуть так, чтобы оно стало равным другому.
	Необходимо вернуть _количество пар_ `(i, j)`, где `0 <= i < j < dominoes.length`, и _домино_ `dominoes[i]` _является **эквивалентным**_ `dominoes[j]`.
	
**Example:**
	**Example 1:**
		**Input:** dominoes = {{1,2}, {2,1}, {3,4}, {5,6}}
		**Output:** 1
	**Example 2:**
		**Input:** dominoes = {{1,2}, {1,2}, {1,1}, {1,2}, {2,2}}
		**Output:** 3
**Constraints:**
	`1 <= dominoes.length <= 4 * 104`
	`dominoes[i].length == 2`
	`1 <= dominoes[i][j] <= 9`
	
Answer:
	Time Complexity: Best - O(n)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    struct hash_pair {
	    size_t operator()(const pair<int, int>& p) const {
	        return p.first * 31 + p.second;
	    }
	};
	
	int numEquivDominoPairs(vector<vector<int>>& dominoes, int maxC = 0) {
	    unordered_map<pair<int, int>, pair<int, int>, hash_pair> allPairs;
	
	    int* secondD = 0; pair<int, int> currentDomino;
	    for (vector<int>& domino : dominoes) {
	        if (domino[0] > domino[1]) swap(domino[0], domino[1]);
	        currentDomino = { domino[0], domino[1] };
	
	        secondD = &allPairs[currentDomino].second;
	        if (*secondD > 0)
	            maxC -= *secondD;
	
	        *secondD = (allPairs[currentDomino].first) + *secondD;
	        maxC += *secondD;
	
	        allPairs[currentDomino].first++;
	    }
	
	    return maxC;
	}
};
```

**Explanation:**
	Цель: Есть эквивалентные домино ( {1,2} и {2,1}), из них можно составить пару. Нужно посчитать количество всех возможных пар таких домино.
	Решение: Можно составить [[Hash table]] где для каждой доминошки будет соотвествовать количество таких доминошек в массиве и сколько пар можно составить из данного количества домино.(Будет выглядеть так ***хештаблица<домино(пара<вверх, низ>), пара<количество домино, количество пар>***)
	Чтобы посчитать количество возможных пар, для данной домино с данным количеством пар, можно просто прибавлять к количеству пар количество домино на каждом шаге для каждой домино. Т.е. берется доминошка, для ее количество пар прибавляется количество доминошек, а потом добавляется плюс один к количеству домино.
	В итоге нужно просто проходится по каждой домино и добавлять все эти параметры к ней, параллельно считая все возможные пары для всех домино.