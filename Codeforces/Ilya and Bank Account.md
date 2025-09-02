**Complexity:** 900
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int n; cin >> n;
    if (n >= 0) {
        cout << n << endl;
    } else {
        int f = n/10;
        int s = (f/10)*10+(n%10);
        cout << max(f, s) << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дано число, можно удалиь последнюю, предпоследнюю или ничего не делать. Нужно вернуть какое макисмлаьноечисло можно получить.
	Решение: Если число больше или равно нуля - вернуть его, иначе проверить какое чисо больше, у которого нету ппоследенего или предпоследнего числа.