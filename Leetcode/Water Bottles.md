**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int numWaterBottles(int numBottles, int numExchange) {
	    int fullBottles = numBottles;
	    int emptyBottles = 0;
	
	    int ans = 0;
	    while (fullBottles) {
	        emptyBottles += fullBottles;
	        ans += fullBottles;
	        fullBottles = 0;
	
	        fullBottles = emptyBottles / numExchange;
	        emptyBottles = (emptyBottles % numExchange);
	    }
	
	    return ans;
	}
};
```
**Explanation:**
	Цель: Даны бутылки с водой, их нужно выпить. Пустые бутылки с водой можно обменять на полные. Нужно узнать сколько бутылок с водой можно выпить.
	Pешение: Выполнять эти действия пока есть полные бутылки с водой.