### `question_302.md`

**Вопрос 302.** В Python-модуле, как сделать функции и переменные, определенные внутри него, доступными извне модуля?

A. Используя функцию `__init__`.
B. Импортируя модуль.
C. Написав `global` перед переменной.
D. Определив блок `__main__`.

**Правильный ответ: B**

**Объяснение:**

Чтобы сделать функции и переменные, определенные в Python-модуле, доступными извне модуля, необходимо *импортировать* этот модуль в другом Python-файле. Это позволяет использовать содержимое модуля, обращаясь к нему через имя модуля.

*   **Вариант A не верен:** Функция `__init__` используется для инициализации *объектов* класса, а не для экспорта элементов модуля.
*   **Вариант B верен:**  Импорт модуля делает его содержимое доступным.
*   **Вариант C не верен:** Ключевое слово `global` делает переменную глобальной *внутри* модуля, но не делает ее доступной извне.
*   **Вариант D не верен:**  Блок `__main__` выполняется только тогда, когда модуль запускается напрямую, и не влияет на его доступность при импорте.

**Как работает импорт модуля:**

1.  Используйте оператор `import module_name` в другом Python-файле.
2.  Python находит файл `module_name.py`, загружает и выполняет код из этого файла.
3.  Создается объект модуля, и становится доступным для использования через `module_name.element`.

**Пример:**

```python
# my_module.py
def my_function():
  return "Hello from my_module"

my_variable = 10

# main.py
import my_module

print(my_module.my_function())  # Output: Hello from my_module
print(my_module.my_variable)  # Output: 10
```

В этом примере, после импорта модуля `my_module` в `main.py`, функции и переменные, определенные в `my_module.py`, становятся доступны для использования через `my_module.my_function` и `my_module.my_variable`.

**В результате:**

Чтобы сделать функции и переменные Python-модуля доступными извне, необходимо использовать оператор `import` для импорта этого модуля в другом Python-файле.

Таким образом, вариант B является правильным.

---

Готов к следующему вопросу!
