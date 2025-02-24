### `question_655.md`

**Вопрос 655.** Что выведет на экран следующий код Python?

```python
def mystery_function(x):
    if x == 0:
        return 0
    return x + mystery_function(x - 1)

print(mystery_function(10))
```

-   A. 10
-   B. 55
-   C. 100
-   D. 0
-   E. Ошибка

**Правильный ответ: B**

**Объяснение:**

Этот код демонстрирует рекурсивную функцию `mystery_function(x)`.

1.  **Функция `mystery_function(x)`:**
    *   **Базовый случай:** Если `x` равно 0, функция возвращает `0`.
    *   **Рекурсивный случай:** Если `x` не равен 0, функция возвращает сумму `x` и результата вызова `mystery_function(x - 1)`.

2.  **Вызов функции:**
    *  `print(mystery_function(10))`:  Вызывает `mystery_function` с аргументом 10, а затем выводит результат.

3.  **Работа рекурсии:**
    *  `mystery_function(10)`  вернет `10 + mystery_function(9)`.
    * `mystery_function(9)` вернет `9 + mystery_function(8)`.
    *  ...
    *   `mystery_function(1)` вернет `1 + mystery_function(0)`.
   *  `mystery_function(0)` вернет `0`.
    *   В результате получится сумма `10 + 9 + 8 + ... + 1 + 0`.

4.  **Вычисление суммы:**
    *   Это сумма чисел от 0 до 10, которая вычисляется по формуле `n * (n + 1) / 2` для n = 10, что равно `10 * 11 / 2 = 55`.

**Разбор вариантов:**
*   **A. 10:** Неправильно.
*   **B. 55:** Правильно.
*   **C. 100:** Неправильно.
*  **D. 0:** Неправильно.
*   **E. Ошибка:** Неправильно. Код выполнится без ошибок.

**В результате:**
*   Функция `mystery_function` вычисляет сумму чисел от 0 до `x`.
*  Рекурсия используется для последовательного вызова функции.

Таким образом, правильным ответом является **B. 55**.
