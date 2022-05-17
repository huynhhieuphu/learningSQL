# Tạo khoá chính

**PRIMARY KEY** : dùng cho 1 (hoặc nhiều) cột không được phép trùng và không null<br><br>

**_Sự khác nhau giữa PRIMARY KEY và UNIQUE:_**<br>

- UNIQUE : tránh trùng, duy nhất + được phép NULL<br>
- PRIMARY KEY : UNIQUE + NOT NULL<br><br>

### Cách 1:

**CREATE TABLE** _table_name_(<br>
id INT PRIMARY KEY<br>
);

### Cách 2:

**CREATE TABLE** _table_name_(<br>
id INT NOT NULL,<br>
PRIMARY KEY(id)<br>
);

### Cách 3: CONSTRAINT - đặt tên cho ràng buộc khoá chính -> dễ quản lý các tên ràng buộc

**CREATE TABLE** _table_name_(<br>
id INT NOT NULL,<br>
CONSTRAINT constraint_pk_name PRIMARY KEY(id)<br>
);

## Trường hợp: Khi đã tạo bảng, rồi xác định cột nào thành PRIMARY KEY

### Cách 1:

**ALTER TABLE** _table_name_ **ADD PRIMARY KEY**(id);

### Cách 2: CONSTRAINT - đặt tên cho ràng buộc khoá chính

**ALTER TABLE** _table_name_ **ADD CONSTRAINT** _constraint_pk_name_ **PRIMARY KEY**(id);

## Trường hợp: Thiết lập 2 cột thành PRIMARY KEY

**CREATE TABLE** _table_name_(<br>
pk_id1 INT NOT NULL,<br>
pk_id2 INT NOT NULL,<br>
PRIMARY KEY(pk_id1, pk_id2)<br>
);

### Huỷ khoá chính

**ALTER TABLE** _table_name_ **DROP CONSTRAINT** _constraint_pk_name_
