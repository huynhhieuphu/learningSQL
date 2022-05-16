# Truy vấn với điều kiện

### Toán tử:

- AND, OR, IN, NOT IN, BETWEEN, NOT BETWEEN, IS NULL, IS NOT NULL
- =, >, <, >=, <=, <> (Not equal to)

**SELECT** \* **FROM** _table_name_ **WHERE** _condition_;

_Ví dụ: lấy ra nhân viên lơn hơn 40 tuổi_

SELECT \* FROM employees<br>  
WHERE YEAR(GETDATE()) - YEAR(birthday) > 40;

```
**YEAR()**    : hàm lấy ra năm
**GETDATE()** : hàm trả ngày-tháng-năm giờ:phút:giây hiện tại (mssql), tương đương **NOW()**: (mysql)
```

_Ví dụ: lấy ra tên, ngày sinh, tuổi nhân viên nhỏ hơn 40 tuổi_

SELECT name, birtday, YEAR(GETDATE()) - YEAR(birthday) AS 'age'<br>
FROM employees<br>
WHERE YEAR(GETDATE()) - YEAR(birthday) < 40;<br>

# Truy vấn với nhiều điều kiện

## Thoả mãn 2 điều kiện mới được

**SELECT** \* **FROM** _table_name_ **WHERE** _condition_1_ **AND** _condition_2_;

_Ví dụ: lấy ra màu sắc liên quan đến sản phẩm đó_

SELECT p.name AS 'Product', c.name AS 'Color', p.'price'<br>
FORM products AS p, product_color AS pc, colors AS c.<br>
WHERE p.id = pc.product_id<br>
AND c.id = pc.color_id<br>

_Ví dụ: lấy số lượng sản phẩm A001 đã bán_

SELECT COUNT(\*) AS 'Sản phẩm A Đã Bán'<br>  
FROM products AS p, order_detail AS od<br>
WHERE p.id = od.product_id<br>
AND p.name = 'A001'<br>

```
Hàm **COUNT()** trả về số dòng
- COUNT(*)      : đếm tất cả các dòng
- COUNT(column) : đếm số dòng của cột
```

## Thoả mãn 1 trong 2 điều kiện đều được

**SELECT** \* **FROM** _table_name_ **WHERE** _condition_1_ **OR** _condition_2_;

_Cú pháp ngắn gọn hơn lệnh OR => IN_

### IN, NOT IN

**SELECT** \* **FROM** _table_name_ **WHERE** _column_name_ **IN** _(value_1, value_2,...)_;

[Tham thảo: SQL IN Operator](https://www.w3schools.com/sql/sql_in.asp)

### BETWEEN, NOT BETWEEN

**SELECT** \* **FROM** _table_name_ **WHERE** _column_name_ **BETWEEN** _value_1_ **AND** _value_2_;

[Tham thảo: SQL BETWEEN Operator](https://www.w3schools.com/sql/sql_between.asp)

### IS NULL, NOT IS NULL

**SELECT** \* **FROM** _table_name_ **WHERE** _column_name_ **IS NULL**;
**SELECT** \* **FROM** _table_name_ **WHERE** _column_name_ **IS NOT NULL**;

[Tham thảo: SQL NULL Values](https://www.w3schools.com/sql/sql_null_values.asp)

_BÀI TẬP: 1. lấy ra danh mục con thuộc danh mục cha trong bảng categories_

SELECT c1.name, c2.name<br>
FORM categories AS c1, categories AS c2<br>
WHERE c1.id = c2.parent_id

```
??? Bài toán: lấy ra sản phẩm đã bán ít 10 lần
> để giải quyết bài toàn dùng Truy vần lồng
```
