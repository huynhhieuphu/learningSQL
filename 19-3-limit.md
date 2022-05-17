# LIMIT

## MSSQL

**SELECT TOP** _number_|**_percent_** _column_name(s)_<br>
**FROM** _table_name_<br>
**WHERE** _condition_;

## MYSQL

### dùng để chỉ định số lượng dòng sẽ được trả về

**SELECT** _column_name(s)_<br>
**FROM** _table_name_<br>
**LIMIT** _number_, _index_;

### hoặc dùng OFFSET => để chỉ số dòng bắt đầu

**SELECT** _column_name(s)_<br>
**FROM** _table_name_<br>
**LIMIT** _number_ **OFFSET** _index_;<br><br>

> Thông thường để phân trang.
