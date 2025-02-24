### `question_880.md`

**Вопрос 880.** Что такое Django ORM, и какие *основные* преимущества он предоставляет разработчикам при работе с базами данных в Django-проектах?

A. Django ORM — это специальный язык запросов, разработанный для Django, который позволяет выполнять сложные операции с базами данных, недоступные в SQL.
B. Django ORM — это инструмент для автоматической генерации HTML-шаблонов на основе данных из базы данных.
C. Django ORM — это система для автоматического развертывания Django-приложений на сервере.
D. Django ORM — это инструмент для объектно-реляционного отображения, который позволяет работать с базой данных, используя Python-классы (models), и предоставляет абстракцию над SQL, упрощая выполнение запросов и создание таблиц.

**Правильный ответ: D**

**Объяснение:**

Django ORM (Object-Relational Mapper) является ключевым компонентом фреймворка Django, который упрощает взаимодействие с базами данных.

1.  **Определение Django ORM**:
    *   ORM — это метод программирования, который преобразует данные между несовместимыми системами типов, используя объектно-ориентированную парадигму.
    *   Django ORM позволяет взаимодействовать с базами данных, используя Python-классы, вместо написания SQL-запросов.

2.  **Преимущества Django ORM:**
    *   **Абстракция от SQL**: Разработчикам не нужно писать SQL-запросы вручную. Django ORM автоматически генерирует SQL-запросы на основе Python-кода.
    *   **Упрощение работы с базой данных**:  Разработчики могут определять структуру базы данных (таблицы, поля, связи) с помощью Python-классов (models).
    *   **Автоматическое создание таблиц:**  Django ORM может автоматически создавать таблицы в базе данных на основе определенных моделей.
    *   **Безопасность:**  Django ORM обеспечивает защиту от SQL-инъекций.
    *   **Переносимость:** ORM позволяет легко переключаться между разными СУБД.
    *   **Удобные методы для запросов:** ORM предоставляет удобные методы для выполнения запросов к базе данных, такие как `filter()`, `get()`, `update()`, `delete()`.

*   **Вариант A не верен:** Django ORM это не язык запросов, а интерфейс.
*   **Вариант B не верен:** Шаблоны генерируются с помощью Django templates.
*   **Вариант C не верен:** Развертывание делается другими инструментами.
*   **Вариант D верен:** Описывает назначение Django ORM.

**В результате:**

Django ORM предоставляет абстракцию над SQL, позволяя разработчикам работать с базами данных, используя Python-классы. Это упрощает выполнение запросов, создание таблиц, повышает безопасность и упрощает перенос приложения между СУБД.

Таким образом, вариант D является правильным.
