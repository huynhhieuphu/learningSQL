# SELECT INTO

> dùng để backup bảng(Tạo ra nhiều bản sao đều được)

**SELECT** _column_name(s)_ **INTO** _clone_table_<br>
**FROM** _table_name_

### Ví dụ: Sao chép 1 bảng mới với bảng có sẵn

SELECT \* INTO clone_product<br>
FROM products;

### Ví dụ: Sao chép 1 bảng mới với các cột chỉ định

SELECT column_1, column_2,... INTO clone_product<br>
FROM products;

### Ví dụ: Sao chép 1 bảng mới với điều kiện

SELECT column_1, column_2,... INTO clone_product<br>
FROM products WHERE price < 10000000;

### Ví dụ: Sao chép 1 bảng mới với 2 hoặc nhiều bảng

SELECT column_1, column_2,... INTO clone_product<br>
FROM products AS p, brands AS b<br>
WHERE p.brand_id = b.id;<br>

> Có thể tạo ra 1 bảng mới không có dữ liệu từ điều kiện sai.
