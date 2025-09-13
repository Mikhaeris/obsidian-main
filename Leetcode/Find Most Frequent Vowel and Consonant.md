**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
int maxFreqSum(string& s) {
	unordered_map<char, int> mp;
	  
	int max_v = 0, max_c = 0;
	for (auto& ch : s) {
		++mp[ch];
		if (isVowel(ch)) {
			max_v = max(max_v, mp[ch]);
		} else {
			max_c = max(max_c, mp[ch]);
		}
	}
	  
	return max_v + max_c;
}
private:
	bool isVowel(char& ch) {
		return ch == 'a' || ch == 'e' || ch == 'i' ||
			   ch == 'o' || ch == 'u';
	}
};
```
**Explanation:**
	Цель: Узнать максимлаьною частоту вхождений гласных и согласных и получить их сумму.
	Pешение: Пройтись по строке,собирая количество повторений всех символов. И параллельно ища максимальное колиечестов поторений для гласных и согласных букв. Вернуть их сумму.
