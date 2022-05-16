# GROUP BY

**SELECT** _column(s)_ **FROM** _table_name_<br>
**WHERE** _condition_<br>
**ORDER BY** _column(s)_<br>
**GROUP BY** _column(s)_;

_Một số quy tắc GROUP BY:_

- Cột hiển thị phải là thuộc tính nằm trong khối GROUP BY hoặc Aggregate Function (các hàm tập hợp)

_Ví dụ: Đếm tất cả sản phẩm đã bán_

SELECT p.name, COUNT(od.id) AS selled<br>
FROM Products AS p<br>
INNER JOIN Order_Details AS od<br>
ON p.id = od.product_id<br>  
GROUP BY p.name

## Agreeate Function

**AVG()** Returns the average value
**COUNT()** Returns the number of rows
**FIRST()** Returns the first value
**LAST()** Returns the last value
**MAX()** Returns the largest value
**MIN()** Returns the smallest value
**ROUND()** Returns a numberic field to the number of decimals specified
**SUM()** Returns the sum

## String Function

**CHARINDEX()** Searches an expression in string expression
and returns its starting position if found

**CONCAT()** Adds two or more strings together

**LEFT()** Extracts a number of characters from a string (starting from left)

**LEN()** / **LENGTH()** Returns the length of the value in text field

**LOWER()** / **LCASE()** Converts character data to lower case

**LRIM()** Removes leading spaces from a string

**SUBTRING** / **MIN()** Extract characters from a text field

**PATINDEX()** returns the position of a pattern in a string

**REPLACE()** replaces all occurrences of a substring within a string, with a new substring

**RIGHT()** Extracts a number of characters from a string (starting from right)

**RTRIM()** Removes trailing spaces from a string

**UPPER()** / **UCASE()** Converts character data to upper case
