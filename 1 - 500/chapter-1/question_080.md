### `question_080.md`

**Вопрос 80.** В Python, что возвращает функция `globals()`?

- A.  Список всех глобальных символов.
- B.  Словарь, представляющий текущую глобальную таблицу символов.
- C.  Значение последнего выражения, вычисленного интерпретатором.
- D.  Список всех локальных символов.

**Правильный ответ: B**

**Объяснение:**

В Python функция `globals()` возвращает словарь, представляющий текущую глобальную таблицу символов.

*   **Вариант A** не верен:  `globals()` возвращает словарь, а не список.
*  **Вариант B** верен: `globals()` возвращает словарь с информацией о глобальных символах.
*   **Вариант C** не верен: Для получения значения последнего выражения используется `_`
*   **Вариант D** не верен: Для локальных переменных используется `locals()`

**Что такое глобальная таблица символов:**

Глобальная таблица символов — это словарь, который содержит все переменные, функции, классы и другие объекты, определенные на уровне модуля (то есть, в глобальной области видимости). Ключами в этом словаре являются имена объектов, а значениями являются сами объекты.

**Как использовать `globals()`:**

Функция `globals()` может быть полезна для:
* **Интроспекции**: Для получения информации о глобальных переменных, функций и классов.
* **Динамическое управление переменными**:  Можно использовать для доступа к глобальным переменным и их значениям динамически.

**Пример:**

```python
global_var: int = 10
def my_function():
    local_var: str = "Hello"
    print(f"Глобальные символы внутри функции: {globals()}")
    print(f"Локальные символы внутри функции: {locals()}")

print(f"Глобальные символы вне функции: {globals()}")

my_function()

# Вывод:
# Глобальные символы вне функции: {'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x...>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': '...', '__cached__': None, 'global_var': 10, 'my_function': <function my_function at 0x...>}
# Глобальные символы внутри функции: {'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x...>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': '...', '__cached__': None, 'global_var': 10, 'my_function': <function my_function at 0x...> }
# Локальные символы внутри функции: {'local_var': 'Hello'}
```

**В результате:**

*   При вызове `globals()` вне функции, словарь содержит все глобальные переменные, определенные в скрипте, включая `global_var` и `my_function`.
*   При вызове `globals()` внутри `my_function()`, словарь покажет те же глобальные переменные.
*  Словарь `locals()` внутри `my_function()` покажет локальные переменные.
Таким образом, **вариант B** является верным.
