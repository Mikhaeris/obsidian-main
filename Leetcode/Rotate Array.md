**Complexity:** Medium
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	void rotate(vector<int>& nums, int k) {
		int n = nums.size();
		k = k % n;
		  
		vector<int> ans(n);
		for (int i = 0; i < n; ++i) {
			ans[(i+k)%n] = nums[i];
		}
		  
		for (int i = 0; i < n; ++i) {
			nums[i] = ans[i];
		}
	}
};
```
**Explanation:**
	Цель: Сдвинуть все элементы в массиве по кругу k раз.
	Решение: Сначала стоить заметить, что сдвигаем массив на его длину массив остается тем же -> можно сорктить эти сдвиги: k = k % nums.size().
	Теперь можно заметить что при сдвиге на самом деле просто последние k элементов переходят вперед. Значит одним циклом заполняем элементы в правильном порядке, т.е. i+k (так как сдвигаем на k) и остаток от n(чтобы последние k жлементов перешли вперед). Записать в изначальный массив.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	void rotate(vector<int>& nums, int k) {
		int n = nums.size();
		k = k % n;
		  
		reverse(nums.begin(), nums.end()-1);
		reverse(nums.begin(), nums.begin()+k-1);
		reverse(nums.begin()+k, nums.end()-1);
	}
	  
private:
	void reverse(vector<int>::iterator start, vector<int>::iterator finish) {
		while (start < finish) {
			auto temp = *start;
			*start++ = *finish;
			*finish-- = temp;
		}
	}
};
```
**Explanation:**
	Цель: Сдвинуть все элементы в массиве по кругу k раз.
	Решение: Если мы просто двигаем псолдение k элементов вправо. То можно заметить, что за самом деле эти элементы находясь в конце оказались в начале относительно k-го числа. Значит можно перевернуть массив и потом перевернуть две частички относительно k.