# INNER JOIN -> lấy ra dữ liệu khoả mãn điều kiện

> Mọi inner join đều cần điều kiện<br>

> inner join --> kiểu kết hợp có điều kiện (trong bài lesson 08) --> sau này có thể không hỗ trợ<br><br>

**SELECT** _column(s)_<br>
**FROM** _table_1_, _table_2_<br>
**WHERE** _table_1.id_ **=** _table_2.id_<br><br>

> inner join --> kiểu mới --> Đúng chuẩn (khuyên dùng)<br><br>
> lấy ra tất cả record khoả điều kiện chung, trường hợp không có sẽ không lấy.

**SELECT** _column(s)_<br>
**FROM** _table_1_ **INNER JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_<br><br>

### Ví dụ: lấy ra tên sp, tên nhãn hàng, giá sp tương ứng

SELECT p.name, b.name, p.price<br>  
FROM products AS p INNER JOIN brands AS b<br>
ON p.brand_id = b.id<br>

## Viết tắt INNER JOIN -> JOIN

**SELECT** _column(s)_<br>
**FROM** _table_1_ **JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_
