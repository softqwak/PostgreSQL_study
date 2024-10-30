
# Шпаргалка по SQL запросам в PostgreSQL

## 1. Основные команды

- **Создание базы данных**:
  ```sql
  CREATE DATABASE имя_бд;
  ```
  Создает новую базу данных с указанным именем.

- **Удаление базы данных**:
  ```sql
  DROP DATABASE имя_бд;
  ```
  Удаляет базу данных с указанным именем. Будьте осторожны, так как эта операция необратима.

- **Создание таблицы**:
  ```sql
  CREATE TABLE имя_таблицы (
      столбец1 тип_данных,
      столбец2 тип_данных,
      ...
  );
  ```
  Создает новую таблицу с указанными столбцами и их типами данных.

- **Удаление таблицы**:
  ```sql
  DROP TABLE имя_таблицы;
  ```
  Удаляет таблицу с указанным именем и все данные в ней.

## 2. Основные операции с данными

- **Вставка данных**:
  ```sql
  INSERT INTO имя_таблицы (столбец1, столбец2, ...)
  VALUES (значение1, значение2, ...);
  ```
  Вставляет новую строку данных в указанную таблицу.

- **Обновление данных**:
  ```sql
  UPDATE имя_таблицы
  SET столбец1 = значение1, столбец2 = значение2
  WHERE условие;
  ```
  Обновляет существующие строки в таблице на основе условия.

- **Удаление данных**:
  ```sql
  DELETE FROM имя_таблицы
  WHERE условие;
  ```
  Удаляет строки из таблицы на основе условия.

- **Выбор данных**:
  ```sql
  SELECT столбец1, столбец2, ...
  FROM имя_таблицы
  WHERE условие
  ORDER BY столбец ASC|DESC
  LIMIT количество;
  ```
  Извлекает данные из таблицы с возможностью фильтрации, сортировки и ограничения количества возвращаемых строк.

## 3. Условия и операторы

- **Условия**:
  ```sql
  WHERE столбец = значение
  WHERE столбец IN (значение1, значение2, ...)
  WHERE столбец LIKE 'шаблон%'
  ```
  Условия для фильтрации данных в запросах.

- **Логические операторы**:
  ```sql
  AND, OR, NOT
  ```
  Операторы для комбинирования условий в WHERE.

## 4. Объединение таблиц

- **INNER JOIN**:
  ```sql
  SELECT *
  FROM таблица1
  INNER JOIN таблица2 ON таблица1.столбец = таблица2.столбец;
  ```
  Объединяет строки из обеих таблиц, где условия соединения выполняются.

- **LEFT JOIN**:
  ```sql
  SELECT *
  FROM таблица1
  LEFT JOIN таблица2 ON таблица1.столбец = таблица2.столбец;
  ```
  Возвращает все строки из первой таблицы и совпадающие строки из второй, если они есть.

## 5. Агрегационные функции

- **Счетчик**:
  ```sql
  SELECT COUNT(*) FROM имя_таблицы;
  ```
  Возвращает общее количество строк в таблице.

- **Среднее**:
  ```sql
  SELECT AVG(столбец) FROM имя_таблицы;
  ```
  Вычисляет среднее значение по указанному столбцу.

- **Минимум и максимум**:
  ```sql
  SELECT MIN(столбец), MAX(столбец) FROM имя_таблицы;
  ```
  Возвращает минимальное и максимальное значение по указанному столбцу.

- **Группировка**:
  ```sql
  SELECT столбец, COUNT(*)
  FROM имя_таблицы
  GROUP BY столбец;
  ```
  Группирует строки по указанному столбцу и вычисляет агрегатные функции.

## 6. Индексы и ограничения

- **Создание индекса**:
  ```sql
  CREATE INDEX имя_индекса ON имя_таблицы (столбец);
  ```
  Создает индекс на указанном столбце для ускорения поиска.

- **Добавление ограничения**:
  ```sql
  ALTER TABLE имя_таблицы
  ADD CONSTRAINT имя_ограничения PRIMARY KEY (столбец);
  ```
  Добавляет ограничение на уникальность для столбца в таблице.