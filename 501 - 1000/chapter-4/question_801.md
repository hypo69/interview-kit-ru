Что такое docstring?
Что такое слайс(slice)?
Почему пустой список нельзя использовать как аргумент по умолчанию?
Для чего нужен метод id()?
Для чего используется ключевое слово yield?
Чем отличаются __iter__ и __next__?
Для чего в классе используется атрибут __slots__?
Какие пространства имен существуют в python?
Зачем нужен pdb?
Каким будет результат следующего выражения?  len(' '.join(list(map(str, [[0], [1]]))))
Когда будет выполнена ветка else в конструкции try…except…else?
Поддерживает ли python множественное наследование?
Как dict и set реализованы внутри? Какова сложность получения элемента? Сколько памяти потребляет каждая структура?
 Что будет напечатано в результате выполнения следующего кода?
 import sys
arr_1 = []
arr_2 = arr_1
print(sys.getrefcount(arr_1))
Что такое дескрипторы? Есть ли разница между дескриптором и декоратором?
Почему всякий раз, когда python завершает работу, не освобождается вся память?
Что будет напечатано в результате выполнения следующего кода?
class Variable:

   def __init__(self, name, value):
      self._name = name
      self._value = value

   @property
   def value(self):
      print(self._name, 'GET', self._value)
      return self._value

   @value.setter
   def value(self, value):
      print(self._name, 'SET', self._value)
      self._value = value

var_1 = Variable('var_1', 'val_1')
var_2 = Variable('var_2', 'val_2')
var_1.value, var_2.value = var_2.value, var_1.value
Что такое интернирование строк? Почему это есть в python?
Почему в python нет оптимизации хвостовой рекурсии? Как это реализовать?
Что такое wheels и eggs? В чём разница?
Как получить доступ к модулю, написанному на python из C и наоборот?
Что такое __pycache__? Что такое файлы .pyc?
