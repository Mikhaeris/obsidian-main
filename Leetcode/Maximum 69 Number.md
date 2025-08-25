**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximum69Number(int num) {
	    int ans = 0;
	    bool flag = false;
	    for (int i = 1000; i > 0; i /= 10) {
	        ans *= 10;
	        if ((num/i)%10 == 6 && flag == false) {
	            ans += 9;
	            flag = true;
	        } else {
	            ans += (num/i)%10;
	        }
	    }
	    return ans;
	}
};
```
**Explanation:**
	Цель: Дано число состоящее из 6 и 9. Нужно сделать из него макимальное изменив только одну 6 или 9 на 9 и 6 соответсвенно.
	Решение: Брать по одному разряду слева направо и если это первая шестерка, то измеянять ее на 9, иначе прибавить этот же разряд. Вернуть полученное число.