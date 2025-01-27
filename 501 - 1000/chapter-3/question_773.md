### `question_773.md`

**Вопрос 773.** Даны два бинарных дерева, представленные в виде своих корней `root1` и `root2`. Разработайте алгоритм на Python для объединения этих деревьев, где значения соответствующих узлов суммируются, и возвращается корень результирующего дерева. В случае если у одного дерева нет дочернего узла, то при этом  результирующем дереве, будут добавлены дочерние узлы из другого дерева.

**Дерево 1:**
```
    1
   / \
  3   2
 /
5
```

**Дерево 2:**

```
    2
   / \
  1  3
   \ /
    4  7

```
**Результирующее дерево:**
```
    4
   /  \
  4   5
 /  \  \
5  4  7
```

**Примеры:**

```
Ввод: root1 = [1, 3, 2, 5], root2 = [2, 1, 3, null, 4, null, 7]
Вывод: [3, 4, 5, 5, 4, null, 7]

Ввод: root1 = [1], root2 = [1, 2]
Вывод: [2, 2]
```
-  A. Для решения задачи нужно с помощью бинарного поиска,  выбрать подходящие узлы, и потом сложить их.
-  B. Для решения задачи нужно  использовать только  рекурсию, и только перебирать значения  листьев.
- C. Для решения задачи нужно использовать  рекурсивный алгоритм, где, в случае если оба узла  не являются `None`, то суммируем их значения и строим новое дерево, а если есть не `None`, то возвращаем его.
-  D. Для решения задачи  нужно  сначала отсортировать оба дерева, а потом  применять сложение.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи слияния бинарных деревьев и суммирования их соответствующих узлов оптимальным является использование рекурсивного алгоритма, поскольку структура бинарного дерева сама по себе является рекурсивной.

*   **Алгоритм (рекурсивный):**
    1. **Рекурсивная функция:**
         *   Создается рекурсивная функция которая принимает два узла `root1` и `root2`.
         *   **Базовый случай:**
              *  Если оба  `root1` и `root2`  являются  `None` то возвращаем  `None`.
              *   Если только  `root1` является  `None`, то возвращаем  `root2`  (поддерево  `root2`).
             *   Если только  `root2`  является `None`, то  возвращаем  `root1` (поддерево  `root1`).
        *   **Суммирование:** Создаем новый узел  `head`, где значение  равно сумме значений  `root1.val` + `root2.val`.
        *  **Рекурсивный вызов:** Рекурсивно вызываем функцию для  левых и правых поддеревьев  `head.left = constructTree(root1.left, root2.left)` и `head.right = constructTree(root1.right, root2.right)`.
       *  **Возвращение  узла:** Функция  возвращает созданный узел `head` (текущее  поддерево).
     2.  **Начальный вызов:**  Вызываем  рекурсию для  двух корней  `root1` и `root2`.
     3.  **Результат:**  Возвращаем корень результирующего дерева.

*   **Преимущества алгоритма:**
    *   **Рекурсивный обход:**  Рекурсия позволяет легко  обходить  бинарное дерево.
    *  **Сохраняет структуру дерева:** Создает новую структуру дерева, с учетом  структур исходных деревьев.
     *  **Суммирует значения:**  Обеспечивает корректное  сложение значений в нужных позициях.
    *  **Эффективность:**  Алгоритм имеет сложность O(n),  где n - число узлов в дереве.

**Примеры (псевдокод):**
```
function constructTree(root1, root2):
    if root1 is null and root2 is null:
        return null
    if root2 is null:
       return root1
     if root1 is null:
          return root2
    root =  new Node with value as sum of current roots
    root.left = constructTree(root1.left, root2.left)
    root.right = constructTree(root1.right, root2.right)
   return root
```
**Примеры реализации в Python:**

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def merge_trees(root1, root2):
        def constructTree(root1, root2):
            if not root1 and not root2:
                return None
            if not root2:
                return root1
            if not root1:
                return root2
            head = TreeNode(root1.val + root2.val)
            head.left = constructTree(root1.left, root2.left)
            head.right = constructTree(root1.right, root2.right)
            return head

        return constructTree(root1, root2)

# helper function for printing results.
def print_tree(root):
    if not root:
      return [None]
    else:
      return [root.val] + print_tree(root.left) + print_tree(root.right)

root1 = TreeNode(1, TreeNode(3, TreeNode(5)), TreeNode(2))
root2 = TreeNode(2, TreeNode(1, None, TreeNode(4)), TreeNode(3, None, TreeNode(7)))
print(f"Ввод: root1 = [1,3,2,5], root2 = [2,1,3,null,4,null,7]")
print(f"Вывод: {print_tree(merge_trees(root1, root2))}")
# Выведет: Вывод: [3, 4, 5, None, None, 5, 4, None, None, None, 7, None, None]

root3 = TreeNode(1)
root4 = TreeNode(1, None, TreeNode(2))
print(f"Ввод: root1 = [1], root2 = [1,2]")
print(f"Вывод: {print_tree(merge_trees(root3, root4))}") # Выведет: [2, None, 2, None, None]
```

**Разбор вариантов:**
*  **A. Для решения задачи нужно использовать метод вставки элементов в дерево на основе их значения, где левый ребенок меньше корня, а правый больше.:** Неправильно. Этот метод не подходит.
*   **B. Для решения задачи необходимо использовать только рекурсивный алгоритм, и только перебирать значения  листьев.:** Неправильно.  Листья  должны быть просуммированы, но нужно обрабатывать все уровни.
*  **C. Для решения задачи нужно использовать рекурсивный алгоритм, который будет складывать значения соответствующих узлов двух деревьев.:** Правильно.
*  **D. Для решения задачи подойдет только итеративный алгоритм со стеком для сохранения узлов.:** Неправильно.

**В результате:**
* Рекурсивный алгоритм позволяет эффективно обходить оба дерева.
*  Функция корректно работает  со всеми возможными структурами.
*   Используется рекурсия для  простого и  лаконичного кода.

Таким образом, правильным ответом является **C. Для решения задачи нужно использовать рекурсивный алгоритм, который будет складывать значения соответствующих узлов двух деревьев.**
