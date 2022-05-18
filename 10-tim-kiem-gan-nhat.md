# Tìm kiếm gần nhất

**SELECT** _column(s)_ **FROM** _table_name_ <br>
**WHERE** _column_name_ **LIKE** **_pattern_**;

### Ví dụ: tìm sản phẩm có ký tự bắt đầu bằng chữ i

SELECT \* FROM products<br>
WHERE LIKE 'i%'

### Ví dụ: tìm sản phẩm có ký tự kết thúc bằng chữ A

SELECT \* FROM products<br>
WHERE LIKE '%A'

### Ví dụ: tìm sản phẩm tồn tại chữ m

SELECT \* FROM products<br>
WHERE LIKE '%m%'

### Ví dụ: tìm sản phẩm tồn tại chữ có unicode (dành cho MSSQL)

SELECT \* FROM products<br>
WHERE LIKE N'%ế%'

> MSSQL Để search được chữ có dấu cần N'%keywords%'.<br>
> MYSQL không phân biệt unicode
