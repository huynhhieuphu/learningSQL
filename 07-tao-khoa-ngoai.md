***Tạo khoá ngoại***

Điều kiện để tạo khoá ngoại
- Tham chiếu tới khoá chính
- cùng kiểu dữ liệu

Ưu điểm
- Đảm bảo toàn vẹn dữ liệu. Không có trường nào tham chiếu tới dữ liệu không tồn tại

Cách 1:

==========================================================
=== CREATE TABLE table_name                            ===
=== (                                                  ===
===   fk_id INT FOREIGN KEY REFERENCES table_pk(id)    ===
=== );                                                 ===
==========================================================

Cách 2:

======================================================
=== CREATE TABLE table_name                        ===
=== (                                              ===
===   fk_id INT,                                   ===
===   FOREIGN KEY fk_id REFERENCES table_pk(id)    ===
=== );                                             ===
======================================================

Trường hợp: Khi đã tạo bảng, rồi xác định cột nào thành FOREIGN KEY

Cách 1:

===========================================================
=== ALTER TABLE table_name                              ===
=== ADD FOREIGN KEY (fk_id) REFERENCES table_pk(id);    ===
===========================================================

Cách 2: CONSTRAINT - đặt tên cho ràng buộc khoá chính

=======================================================
=== ALTER TABLE table_name                          ===
=== ADD CONSTRAINT constraint_fk_name               ===
=== FOREIGN KEY (fk_id) REFERENCES table_pk(id);    ===
=======================================================

***Huỷ khoá phụ***

==================================================================
=== ALTER TABLE table_name DROP CONSTRAINT constraint_fk_name; ===
==================================================================



