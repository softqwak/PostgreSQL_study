
# Основные команды в PostgreSQL с примерами

## 1. Создание базы данных

```sql
CREATE DATABASE my_database;  -- Создает новую базу данных с именем my_database
```

## 2. Удаление базы данных

```sql
DROP DATABASE my_database;  -- Удаляет базу данных с именем my_database. Операция необратима.
```

## 3. Создание таблицы

```sql
CREATE TABLE users (  -- Начинает создание таблицы users
    id SERIAL PRIMARY KEY,  -- Определяет столбец id как SERIAL и первичный ключ
    username VARCHAR(50) NOT NULL,  -- Определяет столбец username с ограничением NOT NULL
    email VARCHAR(100) UNIQUE,  -- Определяет столбец email как уникальный
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP  -- Определяет столбец created_at с текущей датой и временем по умолчанию
);
```

## 4. Удаление таблицы

```sql
DROP TABLE users;  -- Удаляет таблицу users и все данные в ней
```
