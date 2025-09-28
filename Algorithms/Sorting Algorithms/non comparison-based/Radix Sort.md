Поразрядная сортировка - быстрый стабильный алгоритм сортировки.

Идея: Если элементы можно не сравнивать, то можно считать количество их вхождений.

Минусы: Создается дополнительный массив размером с максимальный элемент.

Time Complexity: O(N+M)
Space Complexity: O(N+M)

Алгоритм:
```cpp
void counting_sort(vector<int>& vec, int exp) {
    int n = vec.size();
    
    vector<int> output(n);
    vector<int> count(10);

    for (const auto& el : vec) {
        count[(el / exp) % 10]++;
    }
    
    /* prefix sum */
    for (int i = 0; i < 10; ++i) {
        count[i] += count[i - 1];
    }
    
    for (int i = n - 1; i >= 0; --i) {
        output[count[(vec[i] / exp) % 10]-1] = vec[i];
        count[(vec[i] / exp) % 10]--;
    }

    for (int i = 0; i < n; ++i) {
        vec[i] = output[i];
    }
}

void radix_sort(vector<int>& vec) {
    int max_el = 0;
    for (const auto& el : vec) {
        max_el = max(max_el, el);
    }

    for (int exp = 1; max_el / exp > 0; exp *= 10) {
        counting_sort(vec, exp);
    }
}
```
Объяснение: Находится максимальный элемент. Создается массив count размером с максимальный элемент плюс один(так как отстчет с нуля). Массив count заполняется, где индекс указывает на значение элемента, а значение количество этих элементов. В конце данные из массива count записываются в данный массив, но так же можно создать новый и записать туда.
P.S. В данном случае сортированные данные запишутся в исходный массив!