# INSERT INTO SELECT

> dùng để copy dữ liệu bảng sang 1 bảng khác đã tồn tại.<br>
> điều kiện copy -> tên và kiểu dữ liệu cột phải tương đồng

**INSERT INTO SELECT** _clone_table_<br> **FROM** _table_name_;

_Ví dụ: mysql_

- Bước 1: tạo bảng cần sao chép<br><br>
  **create table** _clone_animals_live_(<br>
  **id int not null auto_increment**,<br>
  _`name`_ **varchar(255) not null**,<br>
  **primary key**(id)<br>
  )<br><br>
- Bước 2: sao chép dữ liệu sang bảng mới<br><br>
  **insert into** _clone_animals_live_(_`name`, id_)<br>
  **select distinct** _live_ **as** _`name`_, _null_ **as** _id_<br>
  **from** _animals_;<br><br>
