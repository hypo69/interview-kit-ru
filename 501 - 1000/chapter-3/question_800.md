### `question_723.md`

**Вопрос 723.** Дан массив целых чисел, в котором все элементы встречаются попарно, за исключением одного уникального элемента. Разработайте алгоритм на Python, который за один проход (линейную сложность) находит этот уникальный элемент.

**Примеры:**

```
Ввод: nums = [2, 1, 5, 5, 2, 1]
Вывод: None (так как нет уникального элемента)

Ввод: nums = [2, 3, 1, 5, 5, 2, 1]
Вывод: 3
```
-   A. Для решения задачи нужно отсортировать массив,  и перебирать элементы.
-   B. Для решения задачи необходимо использовать  цикл с  вложенным циклом для поиска уникального элемента.
-   C. Для решения задачи можно использовать оператор XOR (исключающее ИЛИ), и использовать  свойства этой операции.
-   D. Для решения задачи подходит  хеш-таблица  для отслеживания  количества вхождений, и затем  возврата  одиночного элемента.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи поиска уникального элемента в массиве, где все остальные элементы встречаются попарно, оптимальным является использование побитового XOR (исключающего ИЛИ) оператора. Этот подход позволяет найти уникальный элемент за один проход по массиву (линейная сложность), без использования дополнительных структур данных.

*  **Свойства оператора XOR:**
     *   `x ^ x = 0`:  XOR  числа само на себя равно нулю.
    *   `x ^ 0 = x`: XOR числа  с нулем равно  числу.
   *   **Коммутативность и ассоциативность:**  Позволяет вычислять  результат  в любом порядке.

*   **Алгоритм (побитовый XOR):**
    1.  **Инициализация:**  Инициализируем  переменную `result`  нулем `0`.
    2. **Итерация:**  Итерируемся по всем элементам  массива  `nums`
        *  На каждой итерации  выполняем операцию  побитового  XOR,  между  `result` и  текущим элементом  `num`: `result = result ^ num`.
  3. **Результат:**   После завершения  цикла в `result`  будет  храниться  значение уникального элемента.

*  **Преимущества алгоритма:**
    *  **Линейная сложность:**  Алгоритм выполняет обход массива один раз, что обеспечивает временную сложность `O(n)`.
   * **Постоянная память:**  Использует только константное  кол-во памяти.
    *  **Простота:** Алгоритм легок в реализации и понимании.

**Примеры (псевдокод):**
```
function find_unique_number(nums):
  result = 0
    for num in nums:
      result = result ^ num
    return result
```
**Примеры реализации в Python:**

```python
def find_unique_number(nums):
    result = 0
    for num in nums:
        result ^= num
    return result

nums1 = [2, 1, 5, 5, 2, 1]
print(f"Ввод: nums = {nums1}")
print(f"Вывод: {find_unique_number(nums1)}")  # Выведет: Вывод: 0, нету уникального элемента

nums2 = [2, 3, 1, 5, 5, 2, 1]
print(f"Ввод: nums = {nums2}")
print(f"Вывод: {find_unique_number(nums2)}")   # Выведет: Вывод: 3
nums3 = [1,1,1]
print(f"Ввод: nums = {nums3}")
print(f"Вывод: {find_unique_number(nums3)}") #  Выведет 1

```
**Разбор вариантов:**
*   **A. Для решения задачи нужно отсортировать массив, и перебирать элементы по одному, пока не встретится одиночный элемент.:** Неправильно, сортировка  не нужна и добавит лишней сложности.
*   **B. Для решения задачи необходимо использовать цикл с вложенным циклом для поиска уникального элемента.:** Неправильно. Это приведет к квадратичной сложности O(n^2).
* **C. Для решения задачи можно использовать оператор XOR (исключающее ИЛИ), и использовать свойства этой операции.:** Правильно.
*  **D. Для решения задачи подходит хеш-таблица для отслеживания количества вхождений, и затем возврата одиночного элемента.:**  Неправильно. Хеш-таблица имеет линейную сложность по памяти.

**В результате:**
*   Оператор `XOR` позволяет  найти нечетные дубликаты  элементов в  линейное  время и не требует дополнительной памяти.
*    Алгоритм  обходит массив только один раз и использует свойства XOR.

Таким образом, правильным ответом является **C. Для решения задачи можно использовать оператор XOR (исключающее ИЛИ), и использовать  свойства этой операции.**