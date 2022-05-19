# LEFT JOIN - RIGH JOIN

## LEFT JOIN (LEFT OUTER JOIN)

> Bảng bên phải (table_2) nhập vào chung với bảng bên trái (table_1)<br>
> Record nào Bảng bên phải(table_2) không có thì giá trị đó là NULL

**SELECT** _column(s)_<br>
**FROM** _table_1_ **LEFT JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_<br><br>

> lấy ra các giá trị không có<br><br>

**SELECT** _column(s)_<br>
**FROM** _table_1_ **LEFT JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_
**WHERE** _table_2.id_ **IS NULL**

## RIGHT JOIN (RIGHT OUTER JOIN)

> Bảng bên trái nhập (table_1) vào chung với bảng bên phải (table_2)<br>
> Record nào Bảng bên trái (table_1) không có thì giá trị đó là NULL

**SELECT** _column(s)_<br>
**FROM** _table_1_ **RIGHT JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_<br><br>

> lấy ra các giá trị không có<br><br>

**SELECT** _column(s)_<br>
**FROM** _table_1_ **RIGHT JOIN** _table_2_<br>
**ON** _table_1.id_ **=** _table_2.id_
**WHERE** _table_1.id_ **IS NULL**
