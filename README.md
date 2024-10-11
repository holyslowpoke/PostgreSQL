# PostgreSQL

##SELECT
Select исопльзуется для выбора элемента из таблицы sql
можно использовать FROM если нужно обратиться к конкртеной таблице
также можно использовать псевдонимы для изменения имен 
```sql
SELECT name FROM table;
```
##Column alias (псевдонимы)

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
##ORDER BY
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

##SELECT DISTINCT

SELECT DISTINCT удаляет дубликаты из набоа результатов 
