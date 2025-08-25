**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {
	int n = 0; cin >> n;
	for (; 0 < n; --n) {        
		int rt = 0; cin >> rt;        
		if (rt >= 1900) {            
			cout << "Division 1" << endl;        
		}        
		else if (rt >= 1600) {            
			cout << "Division 2" << endl;        
		}        
		else if (rt >= 1400) {            
			cout << "Division 3" << endl;        
		}        
		else {            
			cout << "Division 4" << endl;        
		}    
	}     
	return 0;
}
```
**Explanation:**
	Цель: Вывести из какого дивизиона.
	Решение: Просто вывести.