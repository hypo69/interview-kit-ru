### `question_188.md`

**Вопрос 188.** Какой из следующих операторов предназначен для перехода к началу следующей итерации цикла в Python?

A. `exit`
B. `break`
C. `continue`
D. `pass`

**Правильный ответ: C**

**Объяснение:**

Оператор `continue` используется для пропуска оставшейся части текущей итерации цикла и немедленного перехода к началу следующей итерации.

*   **Вариант A** не верен:  `exit` завершает программу.
*   **Вариант B** не верен:  `break` прерывает выполнение цикла полностью.
*   **Вариант C** верен:  `continue` переходит к следующей итерации.
*   **Вариант D** не верен: `pass` не выполняет никаких действий.

**Как работает `continue`:**

1.  Когда Python встречает оператор `continue` в цикле, он пропускает все оставшиеся операторы в текущей итерации.
2.  Управление переходит в начало цикла для выполнения следующей итерации.

**Пример:**

```python
for i in range(5):
    if i == 2:
       print("Пропускаем итерацию с i = 2")
       continue # переходим к следующей итерации
    print(f"i = {i}")

# Вывод:
# i = 0
# i = 1
# Пропускаем итерацию с i = 2
# i = 3
# i = 4
```

**В результате:**

*   Когда `i` становится равным 2, текущая итерация пропускается, и программа переходит к следующей.

Таким образом, **вариант C** является правильным.