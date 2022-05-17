# INSERT INTO SELECT

> dùng để copy dữ liệu bảng sang 1 bảng khác đã tồn tại.<br>
> điều kiện copy -> tên và kiểu dữ liệu cột phải tương đồng

**INSERT INTO** _clone_table(columns)_<br>
**SELECT** _old_column(s)_<br>
**FROM** _old_table_;<br><br>

_Ví dụ: mysql_<br>

- Bước 1: tạo bảng cần sao chép, tương ứng với các datatype, ràng buộc của trường trong bảng cũ<br><br>
  **create table** _clone_animals_live_(<br>
  _id_ **int not null auto_increment**,<br>
  _name_ **varchar(255) not null**,<br>
  **primary key**(id)<br>
  )<br><br>
- Bước 2: sao chép dữ liệu sang bảng mới<br><br>
  **insert into** _clone_animals_live_(_name, id_)<br>
  **select distinct** _live_ **as** _name_, _null_ **as** _id_<br>
  **from** _animals_;<br><br>
