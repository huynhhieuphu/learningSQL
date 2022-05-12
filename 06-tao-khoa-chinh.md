***Tạo khoá chính***

PRIMARY KEY : dùng cho 1 (hoặc nhiều) cột không được phép trùng và không null

Sự khác nhau giữa PRIMARY KEY và UNIQUE:
- UNIQUE : tránh trùng, duy nhất + được phép NULL
- PRIMARY KEY : UNIQUE + NOT NULL

Cách 1:

================================
=== CREATE TABLE table_name  ===
=== (                        ===
===   id INT PRIMARY KEY     ===
=== );                       ===
================================

Cách 2:

================================
=== CREATE TABLE table_name  ===
=== (                        ===
===   id INT NOT NULL,       ===
===   PRIMARY KEY(id)        ===
=== );                       ===
================================

Cách 3: CONSTRAINT - đặt tên cho ràng buộc khoá chính -> dễ quản lý các tên ràng buộc

=======================================================
=== CREATE TABLE table_name                	        ===
=== (                                               ===
===   id INT NOT NULL,                              ===
===   CONSTRAINT constraint_pk_name PRIMARY KEY(id) ===
=== );                                              ===
=======================================================

- Trường hợp: Khi đã tạo bảng, rồi xác định cột nào thành PRIMARY KEY

Cách 1:

===================================================
=== ALTER TABLE table_name ADD PRIMARY KEY(id); ===
===================================================

Cách 2: CONSTRAINT - đặt tên cho ràng buộc khoá chính

=================================================================================
=== ALTER TABLE table_name ADD CONSTRAINT constraint_pk_name PRIMARY KEY(id); ===
=================================================================================

- Trường hợp: Thiết lập 2 cột thành PRIMARY KEY

=====================================
=== CREATE TABLE table_name       ===
=== (                             ===
===   pk_id1 INT NOT NULL,        ===
===   pk_id2 INT NOT NULL,        ===
===   PRIMARY KEY(pk_id1, pk_id2) ===
=== );                            ===
=====================================

***Huỷ khoá chính***

=================================================================
=== ALTER TABLE table_name DROP CONSTRAINT constraint_pk_name ===
=================================================================