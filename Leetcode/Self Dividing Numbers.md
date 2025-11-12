**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> selfDividingNumbers(int left, int right) {
        vector<int> vec;
        for (int i = left; i <= right; ++i) {
            if (check_num(i)) {
                vec.push_back(i);
            }
        }
        return vec;
    }
private:
    bool check_num(int num) {
        int cnum = num;

        while (cnum) {
            int r = cnum % 10;
            if (r == 0 || num % r != 0) {
                return false;
            }

            cnum /= 10;
        }
        return true;
    }
```
**Explanation:**
	Цель: Дано два числа, нужно в их диапозоне найти такие числа, что каждое число делится на все цифры в нем и в числе нет нулей.
	Решение: Проверять каждое число от левого диапозона до правого по условию, если подходит, то добавлять в массив.