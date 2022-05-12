LEFT JOIN - RIGH JOIN

***LEFT JOIN***
- Bảng bên phải nhập vào chung với bảng bên trái
- Record nào Bảng bên phải không có thì để NULL

=====================================
=== SELECT column1, column2,...   ===
=== FROM table1 LEFT JOIN table2  ===
=== ON table1.id = table2.id      ===
=====================================

***RIGHT JOIN***
- Bảng bên trái nhập vào chung với bảng bên phải
- Record nào Bảng bên trái không có thì để NULL

======================================
=== SELECT column1, column2,...    ===
=== FROM table1 RIGHT JOIN table2  ===
=== ON table1.id = table2.id       ===     
======================================