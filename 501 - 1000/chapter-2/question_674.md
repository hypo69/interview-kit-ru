### `question_674.md`

**Вопрос 674.** Что такое принцип DRY ("Don't Repeat Yourself") в программировании, и как можно применить этот принцип, используя объектно-ориентированное (ООП) и функциональное программирование (ФП) в Python?

-   A. DRY - это принцип, который рекомендует писать как можно больше кода, чтобы обеспечить его надежность.
-   B. DRY - это принцип разработки, который гласит, что каждый фрагмент кода должен иметь только один источник истины, и он должен быть легко доступен и изменяем. В ООП этот принцип реализуется с помощью наследования, полиморфизма и абстракции, а в ФП - с помощью функций высшего порядка, замыканий и лямбда-выражений.
-   C. DRY - это принцип проектирования баз данных для того, чтобы все данные хранились в одном месте.
-   D. DRY  означает отказ от разделения кода, для упрощения работы с ним.

**Правильный ответ: B**

**Объяснение:**

Принцип DRY (Don't Repeat Yourself) — это фундаментальный принцип разработки программного обеспечения, который призывает избегать дублирования кода. Его суть заключается в том, что каждая часть кода должна иметь только одно,  однозначное представление в системе, чтобы обеспечить легкое сопровождение и внесение изменений.

*   **Основные характеристики принципа DRY:**
    *  **Единственный источник истины:**  Каждая часть логики должна быть определена в одном месте и не должна повторяться в разных местах.
    *   **Избежание дублирования:** Уменьшение количества дублирующегося кода.
     * **Упрощение сопровождения:**  Упрощение внесения изменений, так как требуется  менять только в одном месте.
    *  **Улучшение читаемости:**  Делает код более понятным, так как  повторения не отвлекают от логики.
*   **Применение DRY в ООП:**
    *   **Наследование:** Вынесение общих свойств и методов в базовые классы, а подклассы добавляют или переопределяют их.
    *   **Полиморфизм:**  Позволяет создавать иерархии классов и  обрабатывать их единообразно.
    *   **Абстракция:**  Скрытие деталей реализации и вынесение их в отдельные модули или методы.

*   **Применение DRY в ФП:**
    *   **Функции высшего порядка:** Позволяют создавать более общие функции, переиспользуя  логику.
    *  **Замыкания:**  Позволяют функциям сохранять состояния и создавать более гибкие и повторно используемые функции.
    *    **Лямбда-выражения:**  Позволяют создавать небольшие  функции для кратких задач.
    *  **Композиция:** Соединение простых функций для создания более сложных, тем самым избегая дублирования кода.

**Примеры:**
```python
# ООП: Пример применения DRY с помощью наследования
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"My name is {self.name} and I am {self.age} years old.")

class Student(Person):
    def __init__(self, name, age, major):
        super().__init__(name, age)
        self.major = major

    def introduce(self):
        super().introduce()
        print(f"I am majoring in {self.major}.")

class Teacher(Person):
    def __init__(self, name, age, department):
        super().__init__(name, age)
        self.department = department

    def introduce(self):
        super().introduce()
        print(f"I teach in the {self.department} department.")

# Пример 1: Функциональное программирование и функции высшего порядка.
def add(x, y):
    return x + y
def multiply(x, y):
    return x * y

def apply_operation(func, x, y): # higher order function - принимает функцию как аргумент
    return func(x,y)

print(apply_operation(add, 2,3)) # 5
print(apply_operation(multiply, 2,3)) # 6
# Пример 2 : Функциональное программирование - композиция и лямбды
def add_one(x):
    return x + 1
def multiply_by_two(x):
    return x * 2

composed_func = lambda x: add_one(multiply_by_two(x)) # композиция с лямбда
print(composed_func(5))
```

**Разбор вариантов:**

*   **A. DRY - это принцип, который рекомендует писать как можно больше кода, чтобы обеспечить его надежность.:** Неправильно.
*   **B. DRY - это принцип разработки, который гласит, что каждый фрагмент кода должен иметь только один источник истины, и он должен быть легко доступен и изменяем. В ООП этот принцип реализуется с помощью наследования, полиморфизма и абстракции, а в ФП - с помощью функций высшего порядка, замыканий и лямбда-выражений.:** Правильно.
*  **C. DRY - это принцип проектирования баз данных для того, чтобы все данные хранились в одном месте.:** Неправильно.
*  **D. DRY  означает отказ от разделения кода, для упрощения работы с ним.:** Неправильно.

**В результате:**
*   Принцип DRY позволяет писать более гибкий, переиспользуемый и удобный в сопровождении код.
*  В ООП это достигается с помощью наследования и полиморфизма, а в ФП - за счет использования функций высшего порядка и композиции.
*  Избегание дублирования кода делает код более понятным и предсказуемым.

Таким образом, правильным ответом является **B. DRY - это принцип разработки, который гласит, что каждый фрагмент кода должен иметь только один источник истины, и он должен быть легко доступен и изменяем. В ООП этот принцип реализуется с помощью наследования, полиморфизма и абстракции, а в ФП - с помощью функций высшего порядка, замыканий и лямбда-выражений.**