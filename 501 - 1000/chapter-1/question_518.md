### `question_401.md`

**Вопрос 401.** Какой результат выведет на экран следующий код Python?

```python
my_str = "python"
result = my_str[::-2]
print(result)
```

-   A. `"nhy"`
-   B. `"otp"`
-   C. `"pto"`
-   D. `Error`

**Правильный ответ: B**

**Объяснение:**

Этот код демонстрирует использование срезов (slicing) строк с отрицательным шагом в Python.

1. **Исходная строка:**  `my_str` присваивается значение "python".
2. **Срез строки:** `my_str[::-2]` создает новый срез строки.
    *   Первый двоеточие `:` без указания начального индекса означает, что срез начинается с начала строки.
    *   Второе двоеточие `:` без указания конечного индекса означает, что срез продолжается до конца строки.
    *   `-2` – это шаг, который указывает, что элементы должны выбираться в обратном порядке через один элемент.

3. **Результат среза:**
    *  Срез начнет с последнего символа 'n', затем возьмет предпоследний символ 'o', затем через символ 'h' и т.д
    *   Таким образом, в результате среза будут выбраны символы "n", "t", "p", то есть символы на позициях 5, 3, 1 соответственно.
    *   Поскольку срез идет в обратном порядке, результат будет `"otp"`.

4. **Вывод:**  `print(result)` выводит полученный срез строки.

**Пошаговое выполнение среза `[::-2]`:**

| Индекс | Символ | Включен в результат |
|---|---|---|
| 0 | p |  |
| 1 | y |  o  |
| 2 | t |  |
| 3 | h |  t  |
| 4 | o |  |
| 5 | n |  p  |

**Разбор вариантов:**
*   **A. `"nhy"`**: Неправильно, так как неверно учитывается порядок символов.
*   **B. `"otp"`**: Правильно, срез возвращает строку в обратном порядке с шагом 2
*   **C. `"pto"`**: Неправильно, так как неверно учитывается порядок символов.
*   **D. `Error`**: Неправильно, код выполнится без ошибок.

**В результате:**
*   Срезы строк с отрицательным шагом позволяют легко получать подстроки в обратном порядке.
*   Понимание работы срезов важно для эффективной обработки строк в Python.

Таким образом, правильный ответ **B. `"otp"`**.
