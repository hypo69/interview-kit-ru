### `question_707.md`

**Вопрос 707.** Какой результат выведет на экран следующий код Python?

```python
d = {True: "yes", 1: "no", 1.0: "maybe"}
print(len(d))
```

-   A. 1
-   B. 2
-   C. 3
-   D. `Error`

**Правильный ответ: A**

**Объяснение:**

Этот код демонстрирует поведение словарей при использовании булевых и числовых значений в качестве ключей.

1.  **Словарь `d`:**
    *   `d = {True: "yes", 1: "no", 1.0: "maybe"}`: Создается словарь `d`.
    *  В словарях ключи должны быть уникальными.
    *   `True` и `1`, а также `1.0` имеют одинаковое хеш значение в Python.
    *   Следовательно,   ключи `True` и `1` , и `1.0`  являются дубликатами, а значения, добавляются в словарь, просто перезаписывая предыдущие.
2. **Длина словаря**
   *  Метод `len()`  возвращает кол-во элементов в словаре.
   *  Поскольку в словаре остаются только 1 пара ключ-значение, то  длина словаря равна 1.
3. **Вывод**
   *   Функция  `print(len(d))` выводит длину словаря.

**Разбор вариантов:**
*   **A. 1:** Правильно.
*   **B. 2:** Неправильно.
*  **C. 3:** Неправильно.
*   **D. `Error`:** Неправильно. Код выполнится без ошибок.

**В результате:**
*   В Python `True` имеет хеш, как у целого числа `1`, а `1.0` как у целого числа  `1`,  следовательно, при использовании в словарях они будут заменять друг друга.
*  Поэтому словарь `d` в данном случае будет иметь только один элемент.

Таким образом, правильным ответом является **A. 1**.