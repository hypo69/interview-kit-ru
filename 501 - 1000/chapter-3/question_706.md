### `question_706.md`

**Вопрос 706.** Дана 2D-матрица целых чисел `matrix`, где числа отсортированы по возрастанию как сверху вниз, так и слева направо в каждой строке. Разработайте эффективный алгоритм для определения, присутствует ли заданное целое число `target` в матрице, со сложностью O(log(m\*n)).

**Примеры:**
```
Ввод: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Вывод: True

Ввод: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Вывод: False
```

-   A.  Для решения задачи нужно перебрать все элементы матрицы с помощью двух вложенных циклов.
-   B.  Для решения задачи необходимо отсортировать матрицу и применить бинарный поиск.
-   C. Для решения задачи нужно свести матрицу к одномерному массиву, а затем применить бинарный поиск.
-   D. Для решения задачи, можно использовать бинарный поиск, рассматривая матрицу как отсортированную последовательность и проходя по ней с помощью вычисления координат из индекса.

**Правильный ответ: D**

**Объяснение:**

Для решения задачи поиска элемента в отсортированной 2D-матрице с временной сложностью O(log(m\*n)), наиболее подходящим алгоритмом является адаптация бинарного поиска. Этот алгоритм рассматривает матрицу как отсортированную последовательность, при этом  реальные координаты элемента вычисляются на основе индекса.

*   **Алгоритм (бинарный поиск):**
    1.  **Границы поиска:** Инициализируем левый указатель  `left` как `0` и правый  указатель  `right` как `m * n - 1`, где `m` — количество строк, а `n` — количество столбцов в матрице.
    2.  **Бинарный поиск:**
         * Вычисляем  середину: `mid = left + (right-left)//2`
        *  **Преобразование индекса в координаты:** Вычисляем координаты строки и столбца по индексу `mid`:
               *   `row = mid // n`
               *   `col = mid % n`.
        *  **Сравнение:** Сравниваем значение `matrix[row][col]` с целевым значением `target`.
       * **Условие  бинарного поиска:**
             *  Если `matrix[row][col]` равно  `target` - то  элемент найден.
             *   Если `matrix[row][col]` меньше `target`, то сдвигаем  левую границу на  `mid + 1`.
            *    Если `matrix[row][col]` больше `target`, то сдвигаем правую границу на `mid - 1`.
    3. **Результат:** После завершения бинарного поиска возвращаем `True` если элемент найден, или `False`  если не найден.

* **Преимущества алгоритма:**
     *   **Логарифмическая сложность:** Позволяет достичь временной сложности O(log (m*n)), что значительно более эффективно, чем O(n*m).
     *    **Работает с любыми размерами:** Алгоритм работает с матрицами любых размеров.
     *  **Простота:**   Код достаточно простой для реализации.

**Примеры (псевдокод):**
```
function search_matrix(matrix, target):
    m = number of rows
    n = number of columns
    left = 0
    right = m * n - 1
    while left <= right:
        mid = left + (right - left) // 2
        row = mid // n
        col = mid % n
       if matrix[row][col] == target:
           return True
       elif matrix[row][col] < target:
          left = mid + 1
       else:
         right = mid -1
    return False
```
**Примеры реализации в Python:**
```python
def search_matrix(matrix, target):
    m = len(matrix)
    if m == 0:
      return False
    n = len(matrix[0])
    left = 0
    right = m * n - 1

    while left <= right:
        mid = left + (right - left) // 2
        row = mid // n
        col = mid % n
        if matrix[row][col] == target:
            return True
        elif matrix[row][col] < target:
            left = mid + 1
        else:
            right = mid - 1
    return False
matrix1 = [[1,3,5,7],[10,11,16,20],[23,30,34,60]]
target1 = 3
print(f"Ввод: matrix = {matrix1}, target = {target1}")
print(f"Вывод: {search_matrix(matrix1, target1)}") # Выведет: Вывод: True

matrix2 = [[1,3,5,7],[10,11,16,20],[23,30,34,60]]
target2 = 13
print(f"Ввод: matrix = {matrix2}, target = {target2}")
print(f"Вывод: {search_matrix(matrix2, target2)}") # Выведет: Вывод: False
```
**Разбор вариантов:**

*   **A. Для решения задачи нужно перебрать все элементы матрицы с помощью двух вложенных циклов.:** Неправильно. Полный перебор имеет сложность O(n*m).
*  **B. Для решения задачи необходимо отсортировать матрицу и применить бинарный поиск.:** Неправильно. Матрица уже отсортирована.
*   **C. Для решения задачи нужно свести матрицу к одномерному массиву, а затем применить бинарный поиск.:** Неправильно, так как это приведет к дополнительным затратам на выделение памяти.
* **D. Для решения задачи можно использовать бинарный поиск, рассматривая матрицу как отсортированную последовательность и проходя по ней с помощью вычисления координат из индекса.:** Правильно.

**В результате:**
*   Алгоритм бинарного поиска с вычислением координат позволяет искать элементы в отсортированной матрице за `O(log(m*n))`
*   В алгоритме используется механизм разбиения на  две части и проверка серединного элемента.
*   Полученные координаты  позволяют обходить матрицу, как если бы она была одним длинным отсортированным списком.

Таким образом, правильным ответом является **D. Для решения задачи можно использовать бинарный поиск, рассматривая матрицу как отсортированную последовательность и проходя по ней с помощью вычисления координат из индекса.**