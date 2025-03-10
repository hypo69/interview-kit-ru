### `question_021.md`

**Вопрос 21.** В Python-программировании каково значение метода `__init__` в классе и чем он отличается от других методов, которые могут быть определены в классе? В частности, объясните, как функции `__init__` работают в объектно-ориентированном программировании, включая ее роль в создании объектов, и сравните это с такими методами, как `__str__` и пользовательские функции, которые могут быть добавлены позже в класс.

- A. Метод `__init__` отвечает за инициализацию вновь созданных объектов, действуя как конструктор, задавая начальное состояние или свойства экземпляра при создании объекта.
- B. Метод `__init__` предоставляет строковое представление объекта, в основном для целей отладки, и может быть вызван напрямую для просмотра отформатированной строки.
- C. Метод `__init__` используется для определения того, как экземпляры класса должны быть выведены в удобочитаемом формате в консоль, обычно вызывается при использовании `print()` или `str()`.
- D. Метод `__init__` — это метод, автоматически вызываемый после выполнения любой функции внутри класса, предоставляющий механизм очистки неиспользуемых переменных.

**Правильный ответ: A**

**Объяснение:**

Метод `__init__` — это специальный метод (также известный как "конструктор") в Python, который автоматически вызывается при создании нового экземпляра класса. Он играет ключевую роль в процессе инициализации объекта, устанавливая его начальное состояние и значения его атрибутов.

Давайте разберем каждый из вариантов:

*   **Вариант A**: Утверждает, что `__init__` отвечает за инициализацию объекта как конструктор. Это верное утверждение. Он задает начальное состояние нового экземпляра.
*   **Вариант B**: Описывает роль метода `__init__` как метода предоставляющего строковое представление объекта. Это неправильно, так как строковое представление объекта предоставляет метод `__str__`, а не `__init__`.
*   **Вариант C**: Описывает функцию метода `__init__`, как вывод экземпляров класса в удобочитаемом формате. Это неверно. За это ответственны методы `__str__` и `__repr__`.
*   **Вариант D**: Утверждает, что `__init__` вызывается после выполнения любой функции внутри класса как механизм очистки неиспользуемых переменных. Это тоже неверно.  Метод `__init__` вызывается только при создании нового объекта класса.

**Сравнение с другими методами:**

*   `__str__()` является другим специальным методом в Python, который предназначен для получения "человеко-читаемого" строкового представления объекта. Он вызывается функциями `print()` или `str()`. В отличие от `__init__()`, `__str__()` не используется для инициализации, а для отображения объекта.
    
*   Пользовательские методы (определенные пользователем) — это обычные методы класса, которые могут выполнять любые действия, но их нужно вызывать явно. В отличие от `__init__()`, они не вызываются автоматически при создании объекта.

**Пример:**

```python
class MyClass:
    def __init__(self, name: str, age: int) -> None:
        """Конструктор класса, инициализирующий атрибуты name и age."""
        self.name = name
        self.age = age
        print("Объект создан и инициализирован") # пример дополнительного действия

    def __str__(self) -> str:
        """Возвращает строковое представление объекта."""
        return f"Имя: {self.name}, Возраст: {self.age}"

    def some_method(self) -> None:
        """Обычный пользовательский метод."""
        print("Вызван пользовательский метод")

# Создание объекта (вызывается __init__)
obj1: MyClass = MyClass("Alice", 30) # Вывод: Объект создан и инициализирован
print(obj1)    # Вывод: Имя: Alice, Возраст: 30 (вызывается __str__)
obj1.some_method() # Вывод: Вызван пользовательский метод
```

**В результате:**

*   `__init__()` вызывается при создании `obj1` и инициализирует его атрибуты `name` и `age`.
*   `__str__()` используется функцией print, чтобы получить строковое представление объекта.
*   Метод `some_method()` вызывается явно через `obj1.some_method()`.

Таким образом, **вариант A** является единственным правильным, так как он точно описывает роль и поведение метода `__init__`.
