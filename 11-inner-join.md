INNER JOIN -> lấy ra dữ liệu khoả mãn điều kiện

- Mọi inner join đều cần điều kiện

- inner join -> kiểu kết hợp có điều kiện (trong bài lesson 08) -> sau này có thể không hỗ trợ

===================================
=== SELECT column1, column2,... ===
=== FROM table1, table2         ===
=== WHERE table1.id = table2.id ===     
===================================

- inner join -> kiểu mới -> Đúng chuẩn (khuyên dùng)

=====================================
=== SELECT column1, column2,...   ===
=== FROM table1 INNER JOIN table2 ===
=== ON table1.id = table2.id      ===     
=====================================
	
	Ví dụ: lấy ra tên sp, tên nhãn hàng, giá sp tương ứng

	=================================================
	=== SELECT p.name, b.name, p.price            ===
	=== FROM products AS p INNER JOIN brands AS b ===
	=== ON p.brand_id = b.id                      ===
	=================================================

- Viết tắt INNER JOIN -> JOIN

===================================
=== SELECT column1, column2,... ===
=== FROM table1 JOIN table2.    ===
=== ON table1.id = table2.id    ===     
===================================