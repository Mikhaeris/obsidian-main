**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    unordered_map<char, int> map = {  
    {'T', 4},  
    {'C', 6},  
    {'O', 8},  
    {'D', 12},  
    {'I', 20}};  
  
    int n = 0, ans = 0; cin >> n;  
    for (int i = 0; i < n; i++) {  
        string s; cin >> s;  
        ans += map[s[0]];  
    }  
    cout << ans << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Даны фигуры, нужно посчитать количество граней.
	Tetrahedron - 4, Cube - 6, Octahedron - 8, Dodecahedron - 12, Icosahedron - 20.
	Решение: Составить [[Hash table]] где ключом выступает первая буква, а занчением колчеиство граней. Пройтись и посчитать.