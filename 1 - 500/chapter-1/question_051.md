### `question_051.md`

**Вопрос 051.** На изображении представлены два бинарных дерева. Разработайте алгоритм для вычисления суммы наклонов каждого узла в двоичном дереве, и просуммируйте их.
*   **Наклон узла** - это абсолютная разница между суммой всех значений узла левого поддерева и суммой всех значений узла правого поддерева. Если узел не имеет левого или правого дочернего элемента, то соответствующую сумму считать 0.

**Изображения деревьев в ASCII:**

**Figure A:**

```
    4
   / \
  2   9
 / \   \
3   5   7
```

**Figure B:**

```
    6
   / \
  2  7
 / \  \
0   0  0
```

**Примеры:**

```
Ввод: root = [1,2,3]
Вывод: 1

Ввод: root = [4,2,9,3,5,null,7]
Вывод: 15
```

-   A. Для решения задачи нужно посчитать сумму всех узлов, и  разницу между суммами левого и правого поддерева, а также просуммировать все разницы.
-   B. Для решения задачи нужен алгоритм, основанный на обходе в ширину (BFS) и подсчете разности сумм левого и правого дерева на каждом уровне.
-   C.  Для решения задачи нужен рекурсивный алгоритм, который возвращает сумму поддерева (при этом суммируя наклон текущего узла),  и возвращает сумму наклонов всех узлов.
-  D.  Для решения задачи нужно использовать  рекурсивный алгоритм, который будет вычислять сумму узлов для каждого поддерева, при этом используя алгоритм поиска кратчайшего пути.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи подсчета суммы наклонов всех узлов в бинарном дереве, оптимальным является использование рекурсивного алгоритма, который позволяет эффективно вычислять сумму поддеревьев и наклон каждого узла.

*   **Алгоритм (рекурсивный DFS):**
    1.  **Рекурсивная функция:**  Создадим рекурсивную функцию,  которая возвращает сумму узлов поддерева, и использует ее для вычисления наклона каждого узла.
         *  Если узел является пустым, возвращает 0.
         * Рекурсивно вычисляем сумму левого и правого поддерева.
       *  Наклон текущего узла - это  модуль разности левого и правого поддерева.
         *   Добавляем наклон к общему значению.
       *  Возвращаем сумму узлов поддерева, которая равна сумме значений левого поддерева, правого поддерева и значения  текущего узла.
    2. **Инициализация:** Инициализируем  переменную `total_tilt`, которая будет хранить сумму наклонов.
    3. **Вызов рекурсии:** Вызываем рекурсивную функцию для корня,  и после вызова  вернем `total_tilt`.

*   **Преимущества алгоритма:**
    *   **Рекурсивный обход:** Проходит по всем узлам дерева.
    *  **Сохранение промежуточных сумм:** Промежуточные суммы поддеревьев используется  рекурсивных вычислениях.
    *    **Расчет наклона:** Позволяет рассчитывать наклон каждого узла и добавлять его в общую сумму.
    *   **Эффективность:**   Обеспечивает  эффективную реализацию поиска (O(n)).

**Примеры (псевдокод):**

```
function calculate_tree_tilt(node):
  if node is null:
      return 0
  left_sum = calculate_tree_tilt(node.left)
  right_sum = calculate_tree_tilt(node.right)
  global_sum = global_sum + abs(left_sum - right_sum)
  return node.val + left_sum + right_sum
```

**Примеры реализации в Python:**
```python
#  Реализация BST для тестирования
class TreeNode:
   def __init__(self, val=0, left=None, right=None):
     self.val = val
     self.left = left
     self.right = right

def calculate_tree_tilt(node, total_tilt):
        if not node:
            return 0
        left_sum = calculate_tree_tilt(node.left, total_tilt)
        right_sum = calculate_tree_tilt(node.right, total_tilt)
        total_tilt[0] += abs(left_sum - right_sum)
        return node.val + left_sum + right_sum

root = TreeNode(1,TreeNode(2), TreeNode(3))
total_tilt = [0]
calculate_tree_tilt(root, total_tilt)
print(f"Ввод: root = [1,2,3]")
print(f"Вывод: {total_tilt[0]}") # Выведет: Вывод: 1


root2 = TreeNode(4,TreeNode(2,TreeNode(3),TreeNode(5)), TreeNode(9,None, TreeNode(7)))
total_tilt = [0]
calculate_tree_tilt(root2,total_tilt)
print(f"Ввод: root = [4,2,9,3,5,null,7]")
print(f"Вывод: {total_tilt[0]}")  # Выведет: 15
```
**Разбор вариантов:**
* **A. Для решения задачи нужно посчитать сумму всех узлов, и  разницу между суммами левого и правого поддерева, а также просуммировать все разницы.:** Неправильно. Этот метод только вернет сумму всех наклонов, но требует  использования рекурсии.
*   **B. Для решения задачи нужен алгоритм, основанный на обходе в ширину (BFS) и подсчете разности сумм левого и правого дерева на каждом уровне.:** Неправильно. Хотя BFS и возможен, но не является оптимальным.
*   **C. Для решения задачи нужен рекурсивный алгоритм, который возвращает сумму поддерева (при этом суммируя наклон текущего узла),  и возвращает сумму наклонов всех узлов.:** Правильно.
*   **D. Для решения задачи нужно использовать  рекурсивный алгоритм, который будет вычислять сумму узлов для каждого поддерева, при этом используя алгоритм поиска кратчайшего пути.:** Неправильно. Алгоритм поиска кратчайшего пути не нужен для этой задачи.

**В результате:**
*  Рекурсия позволяет эффективно обработать все узлы дерева.
*  Правильно обьеденение промежуточных результатов вычислений в рекурсии позволяет получить окончательный результат.
*  Используем глобальную переменную  `total_tilt` для хранения суммы наклонов.

Таким образом, правильным ответом является **C. Для решения задачи нужен рекурсивный алгоритм, который возвращает сумму поддерева (при этом суммируя наклон текущего узла), и возвращает сумму наклонов всех узлов.**
