**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int matchPlayersAndTrainers(vector<int>& players, vector<int>& trainers) {  
	    sort(players.begin(), players.end());  
	    sort(trainers.begin(), trainers.end());  
	  
	    int pairs = 0;  
	    for (int p = 0, t = 0; p < players.size() && t <trainers.size();) {  
	        if (players[p] <= trainers[t]) {  
	            ++pairs;  
	            ++p;  
	        }  
	            ++t;  
	    }  
	  
	    return pairs;  
	}
};
```
**Explanation:**
	Цель: Даны тренеры и ироки, нужно найти максимальное количество пар тренер - игрок, в которых умения тренера больше или равняются умениям игрока.
	Решение: Отсортировать оба массива и находить пары, если тренер слабее игрока, то искать такого тренера, пока его умения не будут удовлетворять условиям.
