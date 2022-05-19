# Truy vấn lồng (Sub Query)

## Truy vấn lồng trong WHERE

**SELECT** _column(s)_ **FROM** _table_name_<br>
**WHERE** _condition(s)_ (**SELECT** _column(s)_ **FROM** _table_name_);

### Ví dụ: Kiểm tra mã nhân viên đó có phải là quản lý nhóm không?

SELECT \* FORM employees<br>
WHERE id = '1001' AND id IN (SELECT manager_id FROM employees);<br><br>

- IN : lấy ra các record có giá trị tồn tại bên trong<br>
- NOT IN : lấy ra các record không có tồn tại giá trị

## Truy vấn lồng trong FROM

**SELECT** _column(s)_ **FROM** _table_name_1_, (**SELECT** _column(s)_ **FORM** _table_name_2_) **AS** _table_alias_;

### Ví dụ: Kết hợp 2 bảng mà không cần điều kiện (khi truy vấn lồng trong FROM phải ĐỊNH DANH cho truy vấn lồng)

SELECT _ FROM products, (SELECT _ FROM order_details) AS od;

## Giải bài toán:

1. lấy ra sản phẩm đã bán ít 10 sản phẩm <br>

SELECT \* FROM products AS p<br>
WHERE 10 < (<br>
SELECT COUNT(\*) FROM order_details<br>
WHERE product_id = p.id;<br>
)<br><br>

2. Nhãn hàng nào bán nhiều sp nhất<br>

SELECT \* FROM brands AS b WHERE b.id IN (<br>
SELECT COUNT(\*) FROM products AS p JOIN order_details AS od<br>
ON p.id = od.product_id<br>
WHERE p.brand_id = b.id<br>
);
