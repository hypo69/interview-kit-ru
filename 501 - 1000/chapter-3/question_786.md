### `question_786.md`

**Вопрос 786.** Дан массив целых чисел `nums` размера `n`. Разработайте алгоритм на Python для поиска и возврата мажоритарного элемента в массиве.

*   **Мажоритарный элемент** — это элемент, который появляется в массиве более чем `n / 2` раз, и он всегда существует.

**Примеры:**
```
Ввод: nums = [4, 2, 4]
Вывод: 4

Ввод: nums = [8, 8, 6, 6, 6, 8, 8]
Вывод: 8
```
- A. Для решения задачи нужно использовать сортировку и поиск среднего элемента, который и будет мажоритарным.
- B. Для решения задачи нужно перебрать все элементы массива, и проверить, каждый из них на соответствие условию, т.е. на кол-во вхождений больше чем n/2.
- C.  Для решения задачи нужно использовать  алгоритм  поиска в ширину (BFS).
- D.  Для решения задачи можно использовать алгоритм голосования Бойера-Мура (Boyer-Moore Majority Vote Algorithm), который позволяет найти мажоритарный элемент за один проход с линейной сложностью по времени.

**Правильный ответ: D**

**Объяснение:**

Для решения задачи поиска мажоритарного элемента (элемента, который встречается более чем `n / 2` раз) в массиве, оптимальным является использование алгоритма голосования Бойера-Мура. Этот алгоритм позволяет найти мажоритарный элемент за один проход по массиву (линейное время), без необходимости сортировки или хранения дополнительной информации о каждом элементе.

*   **Алгоритм голосования Бойера-Мура:**
    1.  **Инициализация:** Устанавливаем  кандидата  `candidate`  как `None`,  счетчик  `count`  как `0`.
    2.  **Итерация по массиву:** Перебираем массив `nums`:
        *    Если счетчик равен 0, то  устанавливаем текущий элемент массива как кандидата  `candidate`.
        *  Если текущий элемент равен  кандидату, увеличиваем  счетчик `count`.
        * Если не равен,  то уменьшаем счетчик `count`.
    3. **Проверка:**   Перебираем  массив и считаем количество  вхождений  `candidate`.
     *   Если значение  больше `n/2` то возвращаем  кандидата `candidate`, иначе, если такого  кандидата не существует  возвращаем  `None`.

*   **Преимущества алгоритма:**
    *   **Линейная сложность:** Обеспечивает временную сложность O(n), т.е.  зависит линейно  от  количества  элементов массива.
    *  **Постоянная память:** Требует только постоянный объем  памяти.
    *   **Эффективность:**  Позволяет найти мажоритарный элемент  за один проход.

*   **Почему другие подходы не подходят:**
    *   **Сортировка и поиск среднего:** Сортировка и поиск среднего элемента  не гарантирует нахождение мажоритарного элемента и имеет  сложность O(n log n).
    *   **Полный перебор:** Проверка каждого кандидата на соответствие условию займет квадратичное время `O(n^2)`  и является не эффективной.
    *  **BFS:**  BFS  не применим в данной задаче.

**Примеры (псевдокод):**

```
function majority_element(nums):
    candidate = null
    count = 0
    for element in nums:
        if count == 0:
             candidate = element;
        if element == candidate:
             count = count +1;
        else:
           count  = count -1
     count2 = 0
    for element in nums:
       if element = candidate:
         count2 +=1
    if count2 > length(nums)/2:
      return candidate
    return null
```
**Примеры реализации в Python:**

```python
def find_majority_element(nums):
    candidate = None
    count = 0

    for num in nums:
        if count == 0:
            candidate = num
        if num == candidate:
           count += 1
        else:
          count -= 1

    count2 = 0
    for num in nums:
      if num == candidate:
           count2+=1
    if count2 > len(nums) / 2:
      return candidate
    return None


nums1 = [4, 2, 4]
print(f"Ввод: nums = {nums1}")
print(f"Вывод: {find_majority_element(nums1)}") # Выведет: Вывод: 4

nums2 = [8, 8, 6, 6, 6, 8, 8]
print(f"Ввод: nums = {nums2}")
print(f"Вывод: {find_majority_element(nums2)}") # Выведет: Вывод: 8

nums3 = [1,2,3,4,5,6,7]
print(f"Ввод: nums = {nums3}")
print(f"Вывод: {find_majority_element(nums3)}") # Выведет None
```

**Разбор вариантов:**
*  **A. Для решения задачи нужно использовать сортировку и поиск среднего элемента, который и будет мажоритарным.:** Неправильно.  Сортировка  не эффективна  и не применима для  этой задачи.
* **B. Для решения задачи нужно перебрать все элементы массива, и проверить, каждый из них на соответствие условию, т.е. на кол-во вхождений больше чем n/2.:** Неправильно.  Это решение имеет сложность  `O(n^2)`.
*  **C. Для решения задачи нужно использовать алгоритм  поиска в ширину (BFS).:** Неправильно.
*   **D. Для решения задачи можно использовать алгоритм голосования Бойера-Мура (Boyer-Moore Majority Vote Algorithm), который позволяет найти мажоритарный элемент за один проход с линейной сложностью по времени.:** Правильно.

**В результате:**
*  Алгоритм Бойера Мура  эффективно решает  задачу нахождения мажоритарного элемента.
*  Алгоритм  проходит  массив  только  один раз, и  возвращает  результат  с помощью   эффективных проверок  и  подсчетов.
*   Имеет  линейную  сложность O(n),  что  является  оптимальным решением  задачи.

Таким образом, правильным ответом является **D. Для решения задачи можно использовать алгоритм голосования Бойера-Мура (Boyer-Moore Majority Vote Algorithm), который позволяет найти мажоритарный элемент за один проход с линейной сложностью по времени.**