# FULL OUTER JOIN (MSSQL)

> Lấy ra tất cả dữ liệu khoả mãn điều kiện và không khoả mãn điều kiện<br><br>

**SELECT** _column(s)_<br>
**FROM** _table_1_ **INNER OUTER JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_

> Lưu ý: bên bảng nào không khoả mãn điều kiện sẽ để NULL. <br><br>

### Ví dụ:

SELECT p.name, b.name, p.price<br>
FROM products AS p INNER OUTER JOIN brands AS b<br>
ON p.id = p.brand_id

# CROSS JOIN (MSSQL - MYSQL)

Tổ hợp, mỗi dòng record của bảng A với tất cả record của bảng B (tương tự INNER JOIN)<br><br>

Tổ hợp của 2 bảng, dữ liệu bảng<br>

- bảng A: 1,2,3<br>
- bảng B: x,y<br><br>
  Kết quả:<br>
  1-x<br>
  2-x<br>
  3-x<br>
  1-y<br>
  2-y<br>
  3-y<br><br><br>

**SELECT** _column(s)_<br>
**FROM** _table_1_ **CROSS JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_
