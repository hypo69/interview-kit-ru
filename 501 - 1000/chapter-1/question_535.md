### `question_535.md`

**Вопрос 535.** Какой результат будет получен при выполнении следующего кода Python, 
реализующего алгоритм сортировки слиянием?

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = arr[:mid]
    right = arr[mid:]
    left = merge_sort(left)
    right = merge_sort(right)
    return merge(left, right)

def merge(left, right):
    merged = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            merged.append(left[i])
            i += 1
        else:
            merged.append(right[j])
            j += 1
    merged.extend(left[i:])
    merged.extend(right[j:])
    return merged

# Пример использования
arr = [64, 34, 25, 12, 22, 11, 90]
print("Original array:", arr)
sorted_arr = merge_sort(arr)
print("Sorted array:", sorted_arr)
```

-   A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`
-   B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`
-   C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`
-   D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`

**Правильный ответ: B**

**Объяснение:**

Предоставленный код реализует алгоритм сортировки слиянием (merge sort), который основан на принципе "разделяй и властвуй".

*   **Алгоритм сортировки слиянием:**
    *   Рекурсивно разделяет массив на две половины.
    *   Рекурсивно сортирует каждую половину.
    *   Выполняет слияние отсортированных половин в один отсортированный массив.
*   **Описание кода:**
    *   `merge_sort(arr)`: Функция рекурсивно делит массив `arr` пополам, пока не останутся единичные элементы, а затем вызывает `merge`.
        *   `if len(arr) <= 1`: Базовый случай рекурсии: если длина массива меньше или равна 1, то он возвращается.
        *  `mid = len(arr) // 2`: Находится середина массива.
        *   `left = arr[:mid]`: Левая половина массива.
        *   `right = arr[mid:]`: Правая половина массива.
        *   `left = merge_sort(left)`: Рекурсивный вызов для левой половины.
        *    `right = merge_sort(right)`: Рекурсивный вызов для правой половины.
        *   `return merge(left, right)`: Вызывает функцию `merge` для объединения отсортированных половин.
    *   `merge(left, right)`: Функция объединяет два отсортированных массива `left` и `right` в один отсортированный массив.
        *   `merged = []`:  Инициализируется новый список для объединенных элементов.
        *  `i = j = 0`: Инициализируются индексы для левого и правого массивов.
        *   `while i < len(left) and j < len(right)`: Цикл, который сравнивает элементы из левого и правого массива, добавляя меньший в `merged`.
        *   `merged.extend(left[i:])`: Добавляет оставшиеся элементы из левого массива.
        *   `merged.extend(right[j:])`: Добавляет оставшиеся элементы из правого массива.
        *    `return merged`: возвращает объединенный отсортированный массив.

**Разбор вариантов:**
*   **A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`:** Неправильно, это порядок сортировки по убыванию.
*   **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`:** Правильно. Результат сортировки в порядке возрастания.
*   **C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`:** Неправильно.
*   **D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`:** Неправильно.

**В результате:**
*   Код правильно реализует алгоритм сортировки слиянием для сортировки массива в порядке возрастания.
*  Сортировка слиянием является эффективным алгоритмом сортировки, имеющим гарантированную временную сложность O(n log n).

Таким образом, правильным ответом является **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`**.
