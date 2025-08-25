**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<vector<int>> flipAndInvertImage(vector<vector<int>>& image) {
	for (int i = 0; i < image.size(); ++i) {
		int l = 0, r = image[i].size()-1;
		while (l <= r) {
			if (l != r) {
				int temp = image[i][l];
				image[i][l] = image[i][r];
				image[i][r] = temp;
				image[i][l] ^= 1;
				image[i][r] ^= 1;
			}
			else {
				image[i][l] ^= 1;
			}
				++l;
				--r;
			}
		}
		return image;
	}
};
```
**Explanation:**
	Цель: Дана матрица, нужно перевернуть каждую строку, а потом в каждой строке инвертировать число.
	Решение: Проходится по матрице и переворачивать в нем элементы и параллельно переворачивая последний битю

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<vector<int>> flipAndInvertImage(vector<vector<int>>& image) {
		for (auto &row : image) {
			reverse(row.begin(), row.end());
			for (auto &num : row) {
				num ^= 1;
			}
		}
		return image;
	}
};
```
**Explanation:**
	Цель: Дана матрица, нужно перевернуть каждую строку, а потом в каждой строке инвертировать число.
	Решение: По сути тоже самое решение, только с применением встроенных функций и более карсивым и чистым кодом. Решение не идеально. Но по сути - два цикла(встроеная функция для ревера это все таки цикл), котрые выполнают тоже самое что и один цикл равняются, так как константное время выполение операций присваивания. И еще момент цикл с битовой операцией [[XOR]] буквально летит на скорости света. так что по скорости и по памяти это почти тоже самое(с некоторыми оговорками).

