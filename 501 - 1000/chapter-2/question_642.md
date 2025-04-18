### `question_642.md`

**Вопрос 642.** Как в Python проверить, состоит ли строка только из буквенно-цифровых символов (символов алфавита и цифр)?

- A. Используйте метод `isnumeric()`
- B. Используйте метод `isalpha()`
-  C. Используйте метод `isalnum()`
-  D. Используйте метод `isdecimal()`

**Правильный ответ: C**

**Объяснение:**

В Python для проверки, состоит ли строка только из буквенно-цифровых символов (символов алфавита и цифр), используется встроенный метод `isalnum()`.

*   **Основные характеристики метода `isalnum()`:**
    *   **Буквы и цифры:** Возвращает `True`, если все символы в строке являются буквами (из разных алфавитов) или цифрами (`0`–`9`), и `False` в противном случае.
    *   **Комбинирование:** Строка может содержать как буквы так и цифры.
    *   **Пробелы и специальные символы:** Пробелы, знаки препинания и другие символы не считаются буквенно-цифровыми.
    *  **Строка:** Применяется к строковым объектам.

*   **Разница между  `isalnum()`, `isdigit()`, и `isalpha()`:**
     *  `isalnum()`: - возвращает `True` если все символы в строке это буквы или цифры, или `False` в противном случае
    * `isdigit()`: - возвращает `True` только если все символы это цифры (0-9)
    *  `isalpha()`: - возвращает `True` если все символы это буквы.

**Примеры:**

```python
# Пример 1: Строка только с буквами и цифрами
string1 = 'abc123'
print(f"'{string1}'.isalnum(): {string1.isalnum()}") # Выведет: True
print(f"'{string1}'.isalpha(): {string1.isalpha()}") # Выведет False
print(f"'{string1}'.isnumeric(): {string1.isnumeric()}")  # Выведет: False
print(f"'{string1}'.isdecimal(): {string1.isdecimal()}")   # Выведет False

# Пример 2: Строка с пробельными символами
string2 = 'abc 123'
print(f"'{string2}'.isalnum(): {string2.isalnum()}")  # Выведет: False
print(f"'{string2}'.isalpha(): {string2.isalpha()}")  # Выведет: False
print(f"'{string2}'.isnumeric(): {string2.isnumeric()}") # Выведет: False
print(f"'{string2}'.isdecimal(): {string2.isdecimal()}") # Выведет False
# Пример 3: Строка со спецсимволами
string3 = 'abc-123'
print(f"'{string3}'.isalnum(): {string3.isalnum()}")   # Выведет: False

# Пример 4:  Строка только с буквами
string4 = "hello"
print(f"'{string4}'.isalnum(): {string4.isalnum()}") # Выведет: True
print(f"'{string4}'.isalpha(): {string4.isalpha()}") # Выведет: True
# Пример 5: Строка только с цифрами
string5 = '1234'
print(f"'{string5}'.isalnum(): {string5.isalnum()}") # Выведет: True
print(f"'{string5}'.isnumeric(): {string5.isnumeric()}") # Выведет True
print(f"'{string5}'.isdigit(): {string5.isdigit()}") # Выведет True
print(f"'{string5}'.isdecimal(): {string5.isdecimal()}") # Выведет True
```

**Разбор вариантов:**
*   **A. Используйте метод `isnumeric()`:** Неправильно. Этот метод проверяет состоит ли строка только из числовых символов (например "123"), но не буквенно-цифровых символов.
*  **B. Используйте метод `isalpha()`:** Неправильно. Этот метод проверяет состоит ли строка только из букв, но не цифр.
*   **C. Используйте метод `isalnum()`:** Правильно.
*   **D. Используйте метод `isdecimal()`.:** Неправильно, так как метод проверяет только символы десятичных чисел.

**В результате:**
* Метод  `isalnum()` позволяет проверить, состоит ли строка только из букв и цифр.
*  Пробелы и символы не являются буквенно-цифровыми.
*  Разные методы `isnumeric()`, `isdigit()`, `isdecimal()` позволяют проверять строки на числовое представление.

Таким образом, правильным ответом является **C. Используйте метод `isalnum()`.**
