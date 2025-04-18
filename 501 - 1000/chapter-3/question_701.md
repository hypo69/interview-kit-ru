### `question_701.md`

**Вопрос 701.** Дан массив целых чисел `nums`. Разработайте алгоритм для вычисления наибольшей длины строго возрастающей подпоследовательности (longest increasing subsequence, LIS).

**Примеры:**
```
Ввод: nums = [10,9,2,5,3,7,101,18]
Вывод: 4
Объяснение: подпоследовательность [2,3,7,101] имеет наибольшую длину.

Ввод: nums = [1, 3, 2, 4, 5]
Вывод: 4
Объяснение: подпоследовательность [1, 2, 4, 5] имеет наибольшую длину.
```

-   A.  Для решения задачи необходимо отсортировать массив и получить его длину.
-   B.  Для решения задачи можно использовать только рекурсивный алгоритм, и возвращать максимальное значение среди всех путей.
-   C.  Для решения задачи нужно использовать жадный алгоритм, последовательно выбирая наибольшие значения, удовлетворяющие условию.
-   D.  Для решения задачи можно использовать динамическое программирование, чтобы строить последовательность, сохраняя  значения, для всех возможных подпоследовательностей.

**Правильный ответ: D**

**Объяснение:**

Для нахождения наибольшей длины строго возрастающей подпоследовательности (LIS) в массиве целых чисел, используется алгоритм динамического программирования. Этот алгоритм позволяет эффективно решить задачу, избегая перевычислений.

*  **Алгоритм (динамическое программирование):**
    1.   **Создание массива:**  Создаем массив `dp`, где  `dp[i]`  будет означать длину наибольшей  возрастающей подпоследовательности, заканчивающейся элементом `nums[i]`.
    2. **Инициализация:**   Инициализируем  все значения массива  `dp`  значением  `1`, так как  каждый элемент  является минимальной подпоследовательностью из одного элемента.
    3.   **Заполнение массива:**
         *  Итерируемся по массиву `nums`, и на каждой итерации итерируемся вложенным циклом по всем предыдущим элементам.
         * Если текущий элемент  `nums[i]` больше  предыдущего `nums[j]`, то  `dp[i]`  будет максимальным из  `dp[i]` и `dp[j] + 1` .
        *   Таким образом,  `dp[i]`  будет соответствовать длине наибольшей возрастающей подпоследовательности, которая заканчивается элементом  `nums[i]`.
    4.   **Результат:** После перебора всех элементов, берем максимальное значение из `dp`,  которое соответствует длине LIS.

*   **Преимущества алгоритма:**
    *  **Оптимальность:**  Алгоритм находит наиболее оптимальное решение.
    *   **Динамическое программирование:** Использование  таблицы dp позволяет избежать  перевычислений.
    *  **Оптимальная сложность:** Алгоритм имеет временную сложность `O(n^2)`.

**Примеры (псевдокод):**
```
function longest_increasing_subsequence(nums):
  n = length(nums)
    dp = an array initialized to 1, with the length of nums.
    for i from 1 to n-1:
        for j from 0 to i-1:
          if nums[i] > nums[j]:
            dp[i] = max(dp[i], dp[j] + 1)
    return max(dp)
```
**Примеры реализации в Python:**

```python
def longest_increasing_subsequence(nums):
    n = len(nums)
    dp = [1] * n

    for i in range(1, n):
        for j in range(i):
            if nums[i] > nums[j]:
                dp[i] = max(dp[i], dp[j] + 1)
    return max(dp)

nums1 = [10, 9, 2, 5, 3, 7, 101, 18]
print(f"Ввод: nums = {nums1}")
print(f"Вывод: {longest_increasing_subsequence(nums1)}") # Выведет: Вывод: 4

nums2 = [1, 3, 2, 4, 5]
print(f"Ввод: nums = {nums2}")
print(f"Вывод: {longest_increasing_subsequence(nums2)}") # Выведет: Вывод: 4

nums3 = [1, 1, 1, 1]
print(f"Ввод: nums = {nums3}")
print(f"Вывод: {longest_increasing_subsequence(nums3)}") # Выведет 1
```

**Разбор вариантов:**
*  **A. Для решения задачи необходимо отсортировать массив и получить его длину.:** Неправильно. Сортировка  не поможет решить задачу, так как порядок подпоследовательности должен сохраняться.
*   **B. Для решения задачи можно использовать только рекурсивный алгоритм, и возвращать максимальное значение среди всех путей.:** Неправильно. Рекурсия сама по себе не является оптимальным подходом.
*  **C. Для решения задачи нужно использовать жадный алгоритм, последовательно выбирая наибольшие значения, удовлетворяющие условию.:** Неправильно. Жадный алгоритм не гарантирует нахождение наибольшей подпоследовательности.
*   **D. Для решения задачи можно использовать динамическое программирование, чтобы строить последовательность, сохраняя  значения, для всех возможных подпоследовательностей.:** Правильно.

**В результате:**
*   Алгоритм динамического программирования  находит наибольшую возрастающую подпоследовательность.
*  Строится таблица `dp`, в которой хранится  длина LIS  заканчивающаяся элементом `nums[i]`.
*  Позволяет обойти все варианты, и  найти максимальную длину LIS.

Таким образом, правильным ответом является **D. Для решения задачи можно использовать динамическое программирование, чтобы строить последовательность, сохраняя  значения, для всех возможных подпоследовательностей.**
