### `question_641.md`

**Вопрос 641.** Как в Python проверить, состоит ли строка только из буквенных символов (алфавитных)?

-   A. Используйте метод `isnumeric()`.
-   B. Используйте метод `isletter()`.
-   C. Используйте метод `isalpha()`.
-   D. Используйте функцию `is_alpha()`.

**Правильный ответ: C**

**Объяснение:**

В Python для проверки того, состоит ли строка только из буквенных символов (символов алфавита), используется встроенный метод `isalpha()`.

*  **Метод `isalpha()`:**
    *   **Проверка букв:**  Возвращает `True`, если все символы в строке являются буквами (алфавитными) символами, и `False` в противном случае.
     *  **Различные алфавиты:**  Метод учитывает буквы из разных алфавитов,  то есть не только латинского, но, например, кириллицы или греческого алфавита.
     * **Не учитывает пробелы и знаки препинания:** Пробелы, цифры и другие специальные символы возвращают `False`.
    *   **Строка:** Применяется к строковым объектам.

**Примеры:**

```python
# Пример 1: Строка только с буквами
string1 = 'hello'
print(f"'{string1}'.isalpha(): {string1.isalpha()}")  # Выведет: 'hello'.isalpha(): True

# Пример 2: Строка с цифрами
string2 = 'hello123'
print(f"'{string2}'.isalpha(): {string2.isalpha()}") # Выведет: 'hello123'.isalpha(): False

# Пример 3: Строка с пробелами
string3 = 'hello world'
print(f"'{string3}'.isalpha(): {string3.isalpha()}") # Выведет: 'hello world'.isalpha(): False

# Пример 4: Строка с символами из других алфавитов
string4 = "Привіт"
print(f"'{string4}'.isalpha(): {string4.isalpha()}") # Выведет: 'Привіт'.isalpha(): True

# Пример 5: Пустая строка
string5 = ""
print(f"'{string5}'.isalpha(): {string5.isalpha()}") # Выведет: ''.isalpha(): False
```
**Разбор вариантов:**
*   **A. Используйте метод `isnumeric()`.:** Неправильно. Метод проверяет состоит ли строка из числовых символов, но не из букв.
*   **B. Используйте метод `isletter()`.:** Неправильно,  в Python нет метода `isletter()`.
*  **C. Используйте метод `isalpha()`.:** Правильно.
*  **D. Используйте функцию `is_alpha()`.:** Неправильно.

**В результате:**
*   Метод `isalpha()` позволяет определить, состоит ли строка только из буквенных символов.
*   Пробелы, знаки препинания и цифры не проходят проверку.

Таким образом, правильным ответом является **C. Используйте метод `isalpha()`.**
