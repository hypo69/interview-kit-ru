### `question_637.md`

**Вопрос 637.** В чем разница между магическими методами `__getattr__` и `__getattribute__` в Python, и в каких случаях их использование может быть полезно?

-   A.  Метод `__getattr__` вызывается при попытке получить любой атрибут объекта, а метод `__getattribute__` только при обращении к методам объекта.
-   B.  Метод `__getattribute__` вызывается при попытке получить любой атрибут объекта, а метод `__getattr__` вызывается только при обращении к несуществующим атрибутам.
-   C.  Метод `__getattr__` используется для изменения атрибутов объекта, а `__getattribute__` для получения информации об объекте.
-   D.  Методы `__getattr__` и `__getattribute__` являются взаимозаменяемыми и выполняют одну и туже функцию.

**Правильный ответ: B**

**Объяснение:**

В Python `__getattr__` и `__getattribute__` — это магические методы, которые позволяют контролировать доступ к атрибутам объекта.  Они играют важную роль в механизме доступа к атрибутам и предоставляют возможность  настройки их обработки.

*   **Метод `__getattr__(self, name)`:**
    *   **Вызывается при отсутствии атрибута:**  Метод вызывается только в том случае, если не был найден атрибут с именем `name` с помощью стандартного механизма доступа к атрибутам (`__getattribute__`).
    *   **Обработка несуществующих атрибутов:** Позволяет задать действия по умолчанию, когда к объекту обращаются по несуществующему атрибуту.
    *    **Один аргумент:** принимает имя запрашиваемого атрибута (в виде строки) и возвращает значение.
 *  **Метод `__getattribute__(self, name)`:**
    *   **Управление всеми доступами:** Метод вызывается *каждый раз*, когда происходит обращение к атрибуту объекта, как существующего, так и несуществующего.
    *   **Выполняется всегда:** Вызывается даже в тех случаях, когда атрибут существует и является частью объекта.
    *   **Управление логикой доступа:**  Позволяет контролировать логику доступа ко всем атрибутам.
     *  **Возвращает значение:**  Принимает имя запрашиваемого атрибута (в виде строки) и возвращает значение.

*   **Разница между `__getattr__` и `__getattribute__`:**
    *   `__getattribute__` выполняется *всегда* при обращении к любому атрибуту объекта.
    *   `__getattr__` вызывается только *после* `__getattribute__`, если `__getattribute__` не смог найти требуемый атрибут.
     *  Если вы переопределили `__getattribute__` то вы должны явно вызывать родительский метод, если хотите чтобы механизм работал как обычно.

**Примеры:**

```python
class Missing:
    attr = 42

    def __getattr__(self, name):
        print(f"In __getattr__, asked for {name}")
        return 73

m = Missing()
print(m.attr)  # Вывод: 42
print(m.xyz)  # Вывод: In __getattr__, asked for xyz; 73


class Always:
    attr = 42

    def __getattribute__(self, name):
        print(f"In __getattribute__, asked for {name}")
        return 73

a = Always()
print(a.attr) # Вывод: In __getattribute__, asked for attr; 73
print(a.xyz) # Вывод: In __getattribute__, asked for xyz; 73

class MyClass:
    def __init__(self, name):
       self._name = name
    def __getattribute__(self, name):
        if name.startswith("_"): # если аттрибут начинается с _ то вызываем стандартный механизм.
            return super().__getattribute__(name)
        print(f"getting {name}")
        return super().__getattribute__(name) # вызываем стандартный механизм

    def __getattr__(self, name):
        print(f"in __getattr__ getting {name}")
        return None
c = MyClass("John")
print(c.name) # Выведет getting name\n None
print(c._name) # Выведет John
```

**Разбор вариантов:**

*   **A. Метод `__getattr__` вызывается при попытке получить любой атрибут объекта, а метод `__getattribute__` только при обращении к методам объекта.:** Неправильно.
*    **B. Метод `__getattribute__` вызывается при попытке получить любой атрибут объекта, а метод `__getattr__` вызывается только при обращении к несуществующим атрибутам.:** Правильно.
*  **C. Метод `__getattr__` используется для изменения атрибутов объекта, а `__getattribute__` для получения информации об объекте.:** Неправильно.
*   **D. Методы `__getattr__` и `__getattribute__` являются взаимозаменяемыми и выполняют одну и туже функцию.:** Неправильно.

**В результате:**
*   `__getattribute__` является более общим методом для управления доступом ко всем атрибутам.
*   `__getattr__` используется для обработки несуществующих атрибутов.
*   `__getattribute__`  вызывается всегда (до `__getattr__`).

Таким образом, правильным ответом является **B. Метод `__getattribute__` вызывается при попытке получить любой атрибут объекта, а метод `__getattr__` вызывается только при обращении к несуществующим атрибутам.**