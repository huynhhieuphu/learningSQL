# GROUP BY

**SELECT** _column(s)_ **FROM** _table_name_<br>
**WHERE** _condition_<br>
**ORDER BY** _column(s)_<br>
**GROUP BY** _column(s)_;<br><br>

_Một số quy tắc GROUP BY:_<br>

- Cột hiển thị phải là thuộc tính nằm trong khối GROUP BY hoặc Aggregate Function (các hàm tập hợp)<br><br>

_Ví dụ: Đếm tất cả sản phẩm đã bán_<br>

SELECT p.name, COUNT(od.id) AS selled<br>
FROM Products AS p<br>
INNER JOIN Order_Details AS od<br>
ON p.id = od.product_id<br>  
GROUP BY p.name

## Agreeate Function

**AVG()** Returns the average value<br>
**COUNT()** Returns the number of rows<br>
**FIRST()** Returns the first value<br>
**LAST()** Returns the last value<br>
**MAX()** Returns the largest value<br>
**MIN()** Returns the smallest value<br>
**ROUND()** Returns a numberic field to the number of decimals specified<br>
**SUM()** Returns the sum<br><br>

## String Function

**CHARINDEX()** Searches an expression in string expression
and returns its starting position if found<br>

**CONCAT()** Adds two or more strings together<br>

**LEFT()** Extracts a number of characters from a string (starting from left)<br>

**LEN()** / **LENGTH()** Returns the length of the value in text field<br>

**LOWER()** / **LCASE()** Converts character data to lower case<br>

**LRIM()** Removes leading spaces from a string<br>

**SUBTRING** / **MIN()** Extract characters from a text field<br>

**PATINDEX()** returns the position of a pattern in a string<br>

**REPLACE()** replaces all occurrences of a substring within a string, with a new substring<br>

**RIGHT()** Extracts a number of characters from a string (starting from right)<br>

**RTRIM()** Removes trailing spaces from a string<br>

**UPPER()** / **UCASE()** Converts character data to upper case<br><br>
