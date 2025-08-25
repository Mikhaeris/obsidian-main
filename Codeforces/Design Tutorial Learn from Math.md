**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n; cin >> n;

    vector<char> prime(n+1, true);
    prime[0] = prime[1] = false;

    for (long long i = 2; i*i <= n; ++i) {
        if (prime[i]) {
            for (long long j = i*i; j <= n; j += i) {
                prime[j] = false;
            }
        }
    }
    
    for (int i = 2; i < n-2; ++i) {
        if (!prime[i] && !prime[n-i]) {
            cout << i << " " << n-i << endl;
            break;
        }
    }

    return 0;
}
```
**Explanation:**
	Цель: Дано число, нужно найти два таких числа, которые при сложении давали бы данное и оба числа были составные.
	Решение: С помощью решета Эратосфена найти все простые и все составные числа. Дальше проходится по составным числам в поисках такой пары, что при сложении они давали бы искомое и оба были составные.