**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int distanceTraveled(int mainTank, int additionalTank) {
		int ans = 0;
		while (mainTank >= 5) {
			mainTank -= 5;
			ans += 5 * 10;
			  
			if (additionalTank) {
				mainTank++;
				additionalTank--;
			}
		}
		
		ans += mainTank * 10;
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дано два числа - основной бак и дополнительный. Каждые раз, когда израсходуются 5 литров в основном баке, из дополнительного переливается 1 литр в основной. За 1 литр грузовик проезжает 10 км. Сколько киллометров проедет грузовик.
	Решение: Пока в баке больше или равно 5 литрам, вычитаем из бака 5 литров и к пройденному расстоянию прибавляем 50 км. Если в дополнитлеьном баке есть топливо, то добавляем ы основной бак 1 литр и вычитаем из дополнительного 1 литр. В конце к пройденным километрам добавляем остатки, сколько получится проехать на оставшихся литрах в основном баке. Вернуть ответ.

Answer2:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int distanceTraveled(int mainTank, int additionalTank) {
		int count = mainTank / 5;
		int ans = count * 5;
		  
		mainTank -= ans;
		mainTank += std::min(count, additionalTank);
		additionalTank -= std::min(count, additionalTank);
		  
		if (additionalTank == 0) {
			ans += mainTank;
			return ans * 10;
		}
		  
		if (mainTank >= 5) {
			count = mainTank/5;
			ans += count*5;
			mainTank -= count*5;
			mainTank += std::min(count, additionalTank);
			additionalTank -= std::min(count, additionalTank);
			if (mainTank >= 5) {
				count = mainTank/5;
				ans += count*5;
				mainTank -= count*5;
				mainTank += std::min(count, additionalTank);
				additionalTank -= std::min(count, additionalTank);
				ans += mainTank;
				return ans * 10;
			}
			ans += mainTank;
			return ans * 10;
		}
		  
		ans += mainTank;
		return ans * 10;
	}
};
```
**Explanation:**
	Решение: Чисто интуитивное решение.

Answer3:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int distanceTraveled(int mainTank, int additionalTank) {
		return (mainTank + min((mainTank - 1) / 4, additionalTank)) * 10;
	}
};
```
**Explanation:**
	Решение: Power of Math!