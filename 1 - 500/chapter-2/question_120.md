### `question_120.md`

**Вопрос 20.** В Python, как структура `try-except` обрабатывает поток выполнения, когда возникает ошибка?

- A. Она немедленно останавливает программу при возникновении ошибки, если только ошибка не перехвачена в блоке `except`.
- B. Она перенаправляет поток выполнения в блок `except`, обрабатывая ошибку без остановки программы, если ошибка соответствует исключению, указанному в блоке `except`.
- C. Она игнорирует все ошибки, позволяя программе продолжать выполнение без прерывания.
- D. Она автоматически выводит сообщения об ошибках в консоль, а затем продолжает работу со следующей строки кода.

**Правильный ответ: B**

**Объяснение:**

Структура `try-except` в Python является основным механизмом для обработки исключений. Она позволяет перехватывать и обрабатывать ошибки, которые могут возникнуть во время выполнения программы, тем самым предотвращая ее аварийное завершение.

*   **Вариант A** не верен: Программа не останавливается немедленно при исключении, если оно перехвачено `except`.

*   **Вариант B** верен:  Исключения в блоке `try` перенаправляют поток выполнения в блок `except`, где происходит обработка ошибок.
    
*   **Вариант C** не верен: `try-except` не игнорирует ошибки.

*   **Вариант D** не верен: `try-except` не выводит автоматически ошибки в консоль, это делается явно в блоке except.

**Как работает `try-except`:**

1.  **Блок `try`:** Код, в котором может возникнуть исключение, помещается в блок `try`.
2.  **Блок `except`:** Если внутри блока `try` происходит исключение, Python ищет соответствующий блок `except`, который может обработать возникшее исключение.
3.  **Обработка исключения:** Если соответствующий блок `except` найден, код внутри него выполняется, что позволяет обработать ошибку и продолжить работу программы (или завершить ее более корректно).
4.  **Неперехваченные исключения:**  Если исключение не перехвачено, выполнение программы будет прервано, и будет выведено сообщение об ошибке.

**Пример:**

```python
def divide(x: int, y: int) -> None:
    """Выполняет деление x на y, перехватывая исключение ZeroDivisionError."""
    try:
        result: float = x / y # Может возникнуть ZeroDivisionError
        print(f"Результат деления: {result}")
    except ZeroDivisionError: # Перехват ZeroDivisionError
        print("Ошибка: Деление на ноль!")

divide(10, 2)   # Вывод: Результат деления: 5.0
divide(10, 0)  # Вывод: Ошибка: Деление на ноль!
```
**В результате:**

*   При делении `10 / 2` ошибки не возникнет, и программа выведет результат.
*   При делении `10 / 0` возникнет исключение `ZeroDivisionError`, которое будет перехвачено и выведется сообщение об ошибке.
*   Программа при этом не завершится.

Таким образом, **вариант B** является верным ответом.