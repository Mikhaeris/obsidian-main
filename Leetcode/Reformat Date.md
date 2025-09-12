**Complexity:** Easy
Answer:
	Time Complexity: O(~3N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	string reformatDate(string date) {
		string fdate(10, '-');
		  
		if (!isdigit(date[1])) {
			fdate[8] = '0';
			fdate[9] = date[0];
		} else {
			copy(date.begin(), date.begin() + 2, fdate.begin() + 8);
		}
		  
		unordered_map<string, string> mp = {
			{"Jan", "01"}, {"Feb", "02"}, {"Mar", "03"}, {"Apr", "04"},
			{"May", "05"}, {"Jun", "06"}, {"Jul", "07"}, {"Aug", "08"},
			{"Sep", "09"}, {"Oct", "10"}, {"Nov", "11"}, {"Dec", "12"}
		};
		  
		int c = 5;
		if (date[4] != ' ') --c;
		string month = date.substr(c, 3);
		string rev = mp[month];
		copy(rev.begin(), rev.end(), fdate.begin() + 5);
		  
		int s = 9, f = 13;
		if (date[8] != ' ') --s, --f;
		copy(date.begin() + s, date.begin() + f, fdate.begin());
		  
		return fdate;
	}
};
```
**Explanation:**
	Цель: Перевести строку из одного формата в другой.
	Pешение: Распарсить и перевести.
