### `question_169.md`

**Вопрос 69.** Что делает метод `__repr__()` в классе Python?

A. Он создает новый экземпляр объекта.
B. Он возвращает строковое представление объекта, предназначенное для разработчиков.
C. Он вызывает функцию-конструктор.
D. Он используется для сравнения двух экземпляров объекта.

**Правильный ответ: B**

**Объяснение:**

Метод `__repr__()` в Python используется для возвращения "официального" строкового представления объекта. Это представление предназначено для разработчиков и отладки.

*   **Вариант A** не верен: Для создания нового экземпляра используется метод `__new__()` или вызов конструктора (например, `MyClass()`).
*   **Вариант B** верен: `__repr__()` возвращает строковое представление объекта, которое предназначено для разработчиков.
*   **Вариант C** не верен: Метод `__init__()` является конструктором, а не `__repr__()`.
*   **Вариант D** не верен: Для сравнения объектов используются другие методы, такие как `__eq__()`, `__lt__()` и т.д.

**Как работает `__repr__()`:**

1.  Этот метод вызывается, когда объект выводится в интерактивной консоли Python, или когда используется функция `repr()`.
2.  Он должен возвращать строку, которая может быть использована для создания объекта с такими же атрибутами.
3.  Строка должна быть однозначной и полной информацией для воспроизведения объекта.

**Пример:**

```python
class Point:
    def __init__(self, x: int, y: int):
        self.x = x
        self.y = y

    def __repr__(self):
        return f"Point(x={self.x}, y={self.y})"

point: Point = Point(3, 5)
print(point) # Вывод: <__main__.Point object at 0x...> - (вызывается __str__,  если он не определен то __repr__)
print(repr(point)) # Вывод: Point(x=3, y=5) (вызывается __repr__)
point # Вывод: Point(x=3, y=5) (вызывается __repr__)
```
**В результате:**
* Если в классе не определен `__str__()` и используется `print()`, то Python автоматически вызовет `__repr__()`.
*   При вызове `repr()` или при прямом выводе объекта в интерактивном режиме, вызывается метод `__repr__()`, который возвращает строку, представляющую объект.

Таким образом, **вариант B** является правильным ответом.