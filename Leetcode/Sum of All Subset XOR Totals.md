**Complexity:** Easy
Answer1:
	Time Complexity: O(N^2)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	void plusOne(std::string& numStr) {
        bool flag = true;
        for (int i = numStr.size() - 1; i >= 0 && flag; --i) {
            if (numStr[i] == '1') {
                numStr[i] = '0';
            }
            else {
                numStr[i] = '1';
                flag = false;
            }
        }
        if (flag) {
            numStr = '1' + numStr;
        }
    }

    int subsetXORSum(vector<int>& nums) {
        string numStart(nums.size(), '0');
        const std::string numFinish(nums.size(), '1');
        
        int sum = 0;
        while (numStart != numFinish) {
            plusOne(numStart);
            int temp_sum = 0;
            for (int i = 0; i < numStart.size(); i++) {
                if (numStart[i] == '1') {
                    temp_sum ^= nums[i];
                }
            }
            sum += temp_sum;
        }

        return sum;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно посчитать для всех возможных подмножеств XOR и сложить.
	Решение: Подход грубой силы - находить все комбинации и вычислять XOR для какждого подмножетсва и потом складывать.

**Complexity:** Easy
Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int subsetXORSum(vector<int>& nums) {
		int total = 0;
		for (int num : nums) {
			total |= num;
		}
		return total * (1 << (nums.size() - 1));
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно посчитать для всех возможных подмножеств XOR и сложить.
	Решение: Так как в массиве n элементов - значит всего подмножеств 2^n.
	Значит для числа подстчитанного из OR всх числе массиво тоже едействиует это правило и так можно подсчитать сумму всех подмножеств по XOR.