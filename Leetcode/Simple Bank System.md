**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Bank {
public:
    Bank(vector<long long>& balance) {
        balance_ = balance;
    }
    
    bool transfer(int account1, int account2, long long money) {
        if (!check_account_idx(account1) || !check_account_idx(account2)) return false;
        if (insufficient_funds(account1, money)) return false;
        withdraw(account1, money);
        deposit(account2, money);
        return true;
    }
    
    bool deposit(int account, long long money) {
        if (!check_account_idx(account)) return false;
        balance_[account-1] += money;
        return true;
    }
    
    bool withdraw(int account, long long money) {
        if (!check_account_idx(account)) return false;
        if (insufficient_funds(account, money)) return false;
        balance_[account-1] -= money;
        return true;
    }

private:
    bool check_account_idx(const int& account) {
        return (0 < account && account <= balance_.size());
    }

    bool insufficient_funds(const int& account, const long long& money) {
        return (balance_[account-1] < money);
    }

private:
    vector<long long> balance_;
};
```
**Explanation:**
	Цель: Дан массив аккаунтов, нужно сделать простую банковскую систему.
	Решение: Проводить нужные операции.