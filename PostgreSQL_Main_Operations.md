# Основные операции с данными в PostgreSQL

## 1. Вставка данных

Вставка данных позволяет добавлять новую информацию в таблицу. Пример SQL-запроса:

```sql
INSERT INTO users (username, email)  -- Указываем таблицу users и столбцы, в которые будем добавлять данные
VALUES ('john_doe', 'john@example.com');  -- Указываем значения для этих столбцов
```

### Пояснение:
- `INSERT INTO users` — указывает, что мы добавляем данные в таблицу `users`.
- `(username, email)` — перечисляем столбцы, в которые будем вставлять данные.
- `VALUES ('john_doe', 'john@example.com')` — указываем соответствующие значения для каждого столбца. Каждый элемент в скобках соответствует своему столбцу.

## 2. Обновление данных

Обновление данных позволяет изменять существующую информацию в таблице. Пример SQL-запроса:

```sql
UPDATE users  -- Указываем таблицу, в которой будем обновлять данные
SET email = 'john_new@example.com'  -- Указываем новый адрес электронной почты для обновления
WHERE username = 'john_doe';  -- Указываем условие, чтобы изменить данные только для определенного пользователя
```

### Пояснение:
- `UPDATE users` — указывает, что мы обновляем данные в таблице `users`.
- `SET email = 'john_new@example.com'` — устанавливаем новое значение для столбца `email`.
- `WHERE username = 'john_doe'` — указываем условие, чтобы обновить данные только для пользователя с именем `john_doe`. Это важно, чтобы избежать изменения данных у всех пользователей в таблице.

## 3. Удаление данных

Удаление данных позволяет удалить ненужные строки из таблицы. Пример SQL-запроса:

```sql
DELETE FROM users  -- Указываем таблицу, из которой будем удалять данные
WHERE username = 'john_doe';  -- Указываем условие, чтобы удалить только конкретного пользователя
```

### Пояснение:
- `DELETE FROM users` — указывает, что мы удаляем данные из таблицы `users`.
- `WHERE username = 'john_doe'` — устанавливаем условие, чтобы удалить данные только для пользователя с именем `john_doe`. Если не указать условие, будут удалены все строки в таблице, что может привести к потере данных.

## 4. Выбор данных

Выбор данных позволяет извлечь информацию из таблицы. Пример SQL-запроса:

```sql
SELECT username, email  -- Указываем, какие столбцы хотим извлечь
FROM users  -- Указываем таблицу, из которой будем извлекать данные
WHERE email LIKE '%@example.com'  -- Указываем условие для фильтрации
ORDER BY username ASC  -- Указываем, как сортировать результаты (по возрастанию имени)
LIMIT 10;  -- Ограничиваем результат первыми 10 строками
```

### Пояснение:
- `SELECT username, email` — указываем, что хотим получить значения из столбцов `username` и `email`.
- `FROM users` — указываем, что данные извлекаем из таблицы `users`.
- `WHERE email LIKE '%@example.com'` — устанавливаем условие, чтобы выбрать только тех пользователей, чьи электронные адреса заканчиваются на `@example.com`. Символ `%` означает любое количество любых символов.
- `ORDER BY username ASC` — сортируем результаты по столбцу `username` в порядке возрастания. `ASC` означает "по возрастанию", можно использовать `DESC` для сортировки по убыванию.
- `LIMIT 10` — ограничиваем количество возвращаемых строк до 10. Это полезно, когда таблица большая, и мы хотим увидеть только часть данных.
