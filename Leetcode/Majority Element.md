**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int maj = nums.size()/2;
  
        unordered_map<int, int> mp;
  
        for (int i = 0; i < nums.size(); ++i) {
            ++mp[nums[i]];
            if (mp[nums[i]] > maj) {
                return nums[i];
            }
        }
  
        return -1;
    }
};
```
**Explanation:**
	Цель: Дан массив. Нужно найти в нем мажоритальный элемент.
	Мажоритальный элемент - это элемент, который встречается больше n/2.
	Решение: Создать хеш таблицу [[Hash table]], в которой ключ - уникальный элемент, в значение колиечество повторений. Каждый раз проверять на мажоритальность.

Answer2:
	Time Complexity: O(NlogN)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        return nums[nums.size()/2];
    }
};
```
**Explanation:**
	Цель: Дан массив. Нужно найти в нем мажоритальный элемент.
	Мажоритальный элемент - это элемент, который встречается больше n/2.
	Решение: Отсортировать массив и вернуть n/2 элемент.
	Не совсем понимаю как это работает. Но скорее всего n.2 элемент - элемент который встречается чаще всего, значит он будет на месте n/2.

Answer3:
	Time Complexity: O(NlogN)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int majorityElement(vector<int>& nums) {
		int m = 0, i = 0;
		for (const auto& num : nums) {
			if (m != num) {
				(i == 0)
				? m = num
				: --i;
			} else {
				++i;
			}
		}
		return m;
	}
};
```
**Explanation:**
	Цель: Дан массив. Нужно найти в нем мажоритальный элемент.
	Мажоритальный элемент - это элемент, который встречается больше n/2.
	Решение: Если элемент встречается чаще всего в массиве, то можно завести счетчки повторения элементов. Каждый раз когда элемент повторяется увеличивать счетчик, как только счетчик равен нулю, то менять текущий мажорный эдемент. Так как мажорный элемент преобладает, то он в любом случае превзайдет остальные элементы.

