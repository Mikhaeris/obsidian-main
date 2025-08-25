**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {
	int n = 0; cin >> n;
	bool flag = 0;
	for (int i = 0; i < n; i++) {
		cin >> flag;
		if (flag) {
			cout << "HARD" << endl;
			return 0;
		}
	}
	cout << "EASY" << endl;
	return 0;
}
```
**Explanation:**
	Цель: Дана последовательность, нужно проверить, что в ней все нули.
	Решение: Проверять если 1, то возвращать что нет, иначе да.