### `question_198.md`

**Вопрос 198.** Что такое "инкапсуляция" в объектно-ориентированном программировании?

A. Это возможность класса наследовать методы и атрибуты от другого класса.
B. Это возможность обрабатывать объекты разных классов через общий интерфейс.
C. Это принцип сокрытия внутренней реализации объекта и предоставления доступа к ней через публичный интерфейс.
D. Это возможность использовать один и тот же метод для разных типов данных.

**Правильный ответ: C**

**Объяснение:**

Инкапсуляция — это один из фундаментальных принципов объектно-ориентированного программирования, который заключается в объединении данных (атрибутов) и методов, которые работают с этими данными, в одном объекте (классе). При этом доступ к некоторым частям объекта ограничивается, предоставляя доступ к ним только через специально определенный интерфейс.

*   **Вариант A** не верен: Это определение наследования.
*   **Вариант B** не верен: Это определение полиморфизма.
*   **Вариант C** верен: Инкапсуляция означает сокрытие реализации и предоставление доступа через публичный интерфейс.
*  **Вариант D** не верен:  Это описание полиморфизма.

**Как работает инкапсуляция:**

1.  Атрибуты (данные) объекта могут быть объявлены как "защищенные" или "частные", что ограничивает доступ к ним извне класса.
2.  Для работы с такими атрибутами предоставляются специальные методы, так называемые "геттеры" и "сеттеры", которые определяют, как и когда атрибуты могут быть изменены.
3.  Это позволяет контролировать доступ к данным и обеспечивает более надежную и гибкую структуру кода.

**Пример:**

```python
class BankAccount:
    def __init__(self, balance: int):
        self._balance = balance # Protected-атрибут

    def get_balance(self):
        """Метод для получения баланса"""
        return self._balance
    
    def deposit(self, amount: int):
        """Метод для пополнения баланса"""
       if amount > 0:
          self._balance += amount
       else:
         print("Некорректная сумма пополнения")

    def withdraw(self, amount: int):
        """Метод для снятия денег"""
        if amount > 0 and amount <= self._balance:
           self._balance -= amount
        else:
          print("Недостаточно средств")
    
account = BankAccount(1000)
print(f"Баланс: {account.get_balance()}") # Вывод: Баланс: 1000
account.deposit(500)
print(f"Баланс после пополнения: {account.get_balance()}") # Вывод: Баланс после пополнения: 1500
account.withdraw(100)
print(f"Баланс после снятия: {account.get_balance()}") # Вывод: Баланс после снятия: 1400
# account._balance = -10000 # так делать не правильно
```

**В результате:**
*  В классе `BankAccount` атрибут `_balance` является protected и к нему нельзя обратиться напрямую, а только через методы.
*   Это защищает данные объекта от прямого изменения и позволяет контролировать их через специально разработанные методы.

Таким образом, **вариант C** является правильным ответом.