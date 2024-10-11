# PostgreSQL
## Раздел 1. Запрос данных
## SELECT
Select исопльзуется для выбора элемента из таблицы sql
можно использовать FROM если нужно обратиться к конкртеной таблице
также можно использовать псевдонимы для изменения имен 
```sql
SELECT name FROM table;
```
## Column alias (псевдонимы)

```sql
SELECT
  first_name,
  last_name AS surname
FROM
  customers
```
для конкатенции используется оператор || 
```sql
SELECT
  first_name|| ' ' || last_name
FROM
  customers;
```
## ORDER BY
ASC - убывание
DESC - возрастание
```sql
SELECT
  name
FROM
 customers
ORDER BY
  name ASC;
```
Функция LENGTH()принимает строку и возвращает длину этой строки.
Используйте параметры NULLS FIRSTи NULLS LASTдля явного указания порядка NULLс другими ненулевыми значениями.

## SELECT DISTINCT

SELECT DISTINCT удаляет дубликаты из набоа результатов 

## Раздел 2. Фильтрация данных
## CREATE TABLE 
```sql
CREATE TABLE table_name(
  column datatype(length) column_constrain
)
```
### Ограничения
PostgreSQL включает следующие ограничения столбцов:

NOT NULL  – гарантирует, что значения в столбце не могут быть NULL.
UNIQUE – гарантирует уникальность значений в столбце во всех строках одной таблицы.
ПЕРВИЧНЫЙ КЛЮЧ – столбец первичного ключа однозначно идентифицирует строки в таблице. Таблица может иметь один и только один первичный ключ. Ограничение первичного ключа позволяет определить первичный ключ таблицы.
CHECK – гарантирует, что данные должны удовлетворять логическому выражению. Например, значение в столбце цены должно быть нулевым или положительным.
FOREIGN KEY – гарантирует, что значения в столбце или группе столбцов из таблицы существуют в столбце или группе столбцов в другой таблице. В отличие от первичного ключа, таблица может иметь много внешних ключей.

## WHERE
```sql
SELECT
  name
FROM
 customers
WHERE
  name = 'Joe';
 
```
### IN
```sql
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name IN ('Ann', 'Anne', 'Annie');
```
### LIKE
```sql
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name LIKE 'Ann%';
```

### BETWEEN 
```sql
SELECT 
  first_name, 
  LENGTH(first_name) name_length 
FROM 
  customer 
WHERE 
  first_name LIKE 'A%' 
  AND LENGTH(first_name) BETWEEN 3 
  AND 5 
ORDER BY 
  name_length;
```
### (<>) - not contains
```sql
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name LIKE 'Bra%' 
  AND last_name <> 'Motley';
```
## AND - логическое и
Используйте AND оператор для объединения нескольких логических выражений.
## OR - логическое или


Используйте OR оператор для объединения нескольких логических выражений.

## LIMIT
```sql
SELECT 
  select_list 
FROM 
  table_name 
ORDER BY 
  sort_expression 
LIMIT 
  row_count;
```
## FETCH
Нужен для пропуска определнного количества строк и ищвлеть определнное количество 




