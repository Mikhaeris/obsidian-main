**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool isSameAfterReversals(int num) {
        return num == 0 || num % 10 != 0;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно провеить, что после двух переворотов оно все равно останется равмны начаьному числу.
	Pешение: Есть единственный случай, когда чило не будет равно изначальному, - если в конце стоит хотя бы один нуль. Нужно сделать проверку на это. А так же проверить что само число может бытьравно нулю.