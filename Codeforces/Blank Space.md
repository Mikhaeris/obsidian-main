**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {
	int t = 0; cin >> t;
	for (; t > 0; --t) {
		int n = 0; cin >> n;
		int space = 0, cur = 0;
		for (; n > 0; --n) {
			int num = 0; cin >> num;
			if (num != 0) {
				space = max(space, cur);
				cur = 0;
			}
			else {
				++cur;
			}
		}
		cout << max(space, cur) << endl;
	}
	return 0;
}
```
**Explanation:**
	Цель: Найти самый длинный пробел из едениц.
	Решение: Просто считать и сравнивать с максимальным.