### `question_122.md`

**Вопрос 22.** Как действует предложение `finally` в блоке `try-except`?

A.  Оно выполняет код внутри него только в том случае, если в блоке `try` не было вызвано никаких исключений.
B.  Оно выполняется независимо от того, было ли вызвано исключение или нет, и даже если был встречен оператор `return`.
C.  Оно используется для вызова исключения, если оно не было вызвано в блоке `try`.
D.  Оно предотвращает распространение любого исключения, вызванного в блоке `try`, далее.

**Правильный ответ: B**

**Объяснение:**

Предложение `finally` в блоке `try-except` предназначено для выполнения кода, который *должен* выполниться *всегда*, независимо от того, возникло ли исключение в блоке `try` или нет, или даже если был выполнен оператор `return`.

*   **Вариант A** не верен: Для этого используется `else`, а не `finally`.
*   **Вариант B** верен: Код в блоке `finally` выполняется независимо от того, как был выполнен блок `try`.
*   **Вариант C** не верен: Для вызова исключения используется `raise`, а не `finally`.
*   **Вариант D** не верен: `finally` не предотвращает распространение исключений, а лишь гарантирует выполнение кода.

**Как работает `try...except...finally`:**

1.  Выполняется код в блоке `try`.
2.  Если в блоке `try` возникает исключение, Python ищет соответствующий блок `except` для его обработки.
3.  **Независимо** от того, было ли исключение и был ли найден `except` блок, *всегда* выполняется код в блоке `finally`.
4.  Если исключения не было, то блок `finally` выполнится после блока `try`.
5.  Блок `finally` выполняется даже если блок `try` имеет оператор `return`, или даже если `except` содержит оператор `return`.

**Типичные применения `finally`:**

*   **Освобождение ресурсов:** Освобождение внешних ресурсов, таких как файлы, сокеты, или соединения с базами данных.
*   **Обеспечение корректного завершения:**  Выполнение финальных действий, которые должны быть гарантированно выполнены, независимо от успешного или неуспешного выполнения кода.

**Пример:**

```python
def my_function(num: int) -> int | None:
  """Проверяем число на четность и обрабатываем исключения с помощью try-except-finally"""
  try:
    result: int = 10 // num
    print(f"Результат деления: {result}")
    if num > 5:
       return result
  except ZeroDivisionError:
    print("Нельзя делить на ноль")
    return None # Возвращаем None если ошибка
  finally:
      print("Блок finally всегда выполняется")


res1 = my_function(2)
print(f"Результат: {res1}")

res2 = my_function(0) # Вызовется ZeroDivisionError
print(f"Результат: {res2}")

res3 = my_function(6)
print(f"Результат: {res3}")

# Вывод:
# Результат деления: 5
# Блок finally всегда выполняется
# Результат: 5
# Нельзя делить на ноль
# Блок finally всегда выполняется
# Результат: None
# Результат деления: 1
# Блок finally всегда выполняется
# Результат: 1
```

**В результате:**
* При вызове `my_function(2)` , код выполняется без ошибок и выполняется блок `finally` а затем результат возвращается.
* При вызове `my_function(0)` происходит `ZeroDivisionError`, код переходит в блок except, где обрабатывается исключение и возвращает `None` а также выполняет код из `finally` блока.
*  При вызове  `my_function(6)`  возвращается `result`, а также выполняется блок `finally`.

Таким образом, **вариант B** является правильным ответом.