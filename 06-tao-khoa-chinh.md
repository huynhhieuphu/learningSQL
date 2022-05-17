# Tạo khoá chính

**PRIMARY KEY** : dùng cho 1 (hoặc nhiều) cột không được phép trùng và không null<br><br>

**_Sự khác nhau giữa PRIMARY KEY và UNIQUE:_**<br>

- UNIQUE : tránh trùng, duy nhất + được phép NULL<br>
- PRIMARY KEY : UNIQUE + NOT NULL<br><br>

### Cách 1:

**CREATE TABLE** _table_name_(<br>
_id_ **INT PRIMARY KEY**<br>
);

### Cách 2:

**CREATE TABLE** _table_name_(<br>
_id_ **INT NOT NULL,**<br>
**PRIMARY KEY**(_id_)<br>
);

### Cách 3: CONSTRAINT - đặt tên cho ràng buộc khoá chính -> dễ quản lý các tên ràng buộc

**CREATE TABLE** _table_name_(<br>
_id_ **INT NOT NULL,**<br>
**CONSTRAINT** _constraint_pk_name_ **PRIMARY KEY**(_id_)<br>
);

## Trường hợp: Khi đã tạo bảng, rồi xác định cột nào thành PRIMARY KEY

### Cách 1:

**ALTER TABLE** _table_name_ **ADD PRIMARY KEY**(_id_);

### Cách 2: CONSTRAINT - đặt tên cho ràng buộc khoá chính

**ALTER TABLE** _table_name_ **ADD CONSTRAINT** _constraint_pk_name_ **PRIMARY KEY**(_id_);

## Trường hợp: Thiết lập 2 cột thành PRIMARY KEY

**CREATE TABLE** _table_name_(<br>
_pk_id1_ **INT NOT NULL,**<br>
_pk_id2_ **INT NOT NULL,**<br>
**PRIMARY KEY**(_pk_id1, pk_id2_)<br>
);

### Huỷ khoá chính

**ALTER TABLE** _table_name_ **DROP CONSTRAINT** _constraint_pk_name_
