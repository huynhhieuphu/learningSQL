INDEX - Tăng tốc độ truy vấn

??? Tình huống truy vấn với record lên hàng triệu, hàng tỷ thì rất lâu

Ưu điểm: Tốc độ truy vấn nhanh
Nhược điểm: CRUD thì rất lâu

***Tạo INDEX***

- Cho phép các trường trùng nhau

====================================================================
=== CREATE INDEX index_name ON table_name(column1, column2,...); ===
====================================================================

Ví dụ:

	================================================================
	=== CREATE INDEX iOrderDetails ON order_details(product_id); ===
	================================================================

- KHÔNG cho phép các trường trùng nhau

==================================================================================
=== CREATE UNIQUE INDEX unique_index_name ON table_name(column1, column2,...); ===
==================================================================================


Ví dụ:

===============================================
=== CREATE INDEX iProducts ON products(id); ===
===============================================

-- Sử dụng bình thương như câu truy vấn bình thường

***Xoá INDEX***

===================================================== 
=== ALTER TABLE table_name DROP INDEX index_name; ===
=====================================================
