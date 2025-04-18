### `question_789.md`

**Вопрос 789.** Какой результат выведут следующие выражения при их выполнении в Python?

```python
big_num_1 = 1000
big_num_2 = 1000
small_num_1 = 1
small_num_2 = 1
print(big_num_1 is big_num_2)
print(small_num_1 is small_num_2)
```

-   A.  `True True`
-   B. `False False`
-   C. `False True`
-   D. `True False`

**Правильный ответ: C**

**Объяснение:**

Этот код демонстрирует поведение оператора `is` при сравнении целых чисел в Python, и влияние механизма интернирования на работу этого оператора.

1.  **Инициализация переменных:**
    *   `big_num_1 = 1000`, `big_num_2 = 1000`:  Создаются две переменные с одинаковым целым значением 1000.
    *  `small_num_1 = 1`, `small_num_2 = 1`: Создаются две переменные с одинаковым целым значением 1.
2.  **`big_num_1 is big_num_2`:**
    *  `is`  - проверяет идентичность объектов, то есть, ссылаются ли они на один и тот же участок в памяти.
    *  В этом случае, целые числа `1000` не являются малыми целыми числами, и Python  создает для них разные обьекты, которые  не будут интернированы (сохранены в кеше).
    *   Поэтому,  `big_num_1 is big_num_2`  возвращает `False`.
3.  **`small_num_1 is small_num_2`:**
    *   Целые числа от `-5` до `256` в Python кэшируются (интернируются).
    *  Это означает, что если две переменные имеют значения в этом диапазоне, то  они будут ссылаться на один и тот же объект в памяти.
     *   Поэтому,  `small_num_1 is small_num_2`  возвращает `True`.

**Разбор вариантов:**
*   **A. `True True`:** Неправильно.
*   **B. `False False`:** Неправильно.
*   **C. `False True`:** Правильно.
*   **D. `True False`:** Неправильно.

**В результате:**
*  Оператор `is`  сравнивает идентичность обьектов.
*   Маленькие целые числа (от -5 до 256) в  Python интернированы и, соответственно, две разные переменные, имеющие  одно и то же целое значение, будут  ссылаться на один и тот же объект.
*  Для больших чисел Python  не выполняет интернирование (кэширование).

Таким образом, правильным ответом является **C. `False True`**.
