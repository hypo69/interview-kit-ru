### `question_193.md`

**Вопрос 193.** Каким образом метод `__init__` используется в классах Python и как он влияет на создание экземпляров?

A. Он вызывается при удалении объекта, гарантируя освобождение ресурсов.
B. Он вызывается автоматически при создании объекта, устанавливая его начальное состояние.
C. Он вызывается только если вызывается вручную, как обычный метод.
D. Он используется для сравнения двух объектов.

**Правильный ответ: B**

**Объяснение:**

Метод `__init__` в Python является конструктором класса. Он автоматически вызывается при создании нового экземпляра (объекта) класса. Его основная роль состоит в инициализации атрибутов объекта и установлении его начального состояния.

*   **Вариант A** не верен: Метод `__del__` вызывается при удалении объекта.
*   **Вариант B** верен: `__init__` является конструктором и вызывается при создании объекта.
*   **Вариант C** не верен: `__init__` вызывается автоматически, а не вручную.
*   **Вариант D** не верен: Для сравнения используют метод `__eq__`.

**Как работает `__init__`:**

1.  Когда создается новый экземпляр класса, Python автоматически вызывает метод `__init__`.
2.  Первым параметром `__init__` всегда является `self`, который представляет ссылку на создаваемый объект.
3.  Внутри `__init__` устанавливаются начальные значения атрибутов объекта.

**Пример:**

```python
class Person:
    def __init__(self, name: str, age: int):
       """Конструктор класса Person."""
       self.name = name
       self.age = age
       print(f"Создан объект {self.name}")

person1: Person = Person("Alice", 30) # Вывод: Создан объект Alice
print(f"Имя: {person1.name}, Возраст: {person1.age}") # Вывод: Имя: Alice, Возраст: 30
```

**В результате:**

*   При создании объекта `person1`, автоматически вызывается метод `__init__()`, который инициализирует атрибуты `name` и `age`.

Таким образом, **вариант B** является правильным.
