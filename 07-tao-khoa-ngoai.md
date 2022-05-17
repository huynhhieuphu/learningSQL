# Tạo khoá ngoại

> Điều kiện để tạo khoá ngoại
>
> - Tham chiếu tới khoá chính
> - cùng kiểu dữ liệu

### Ưu điểm

- Đảm bảo toàn vẹn dữ liệu. Không có trường nào tham chiếu tới dữ liệu không tồn tại

## Cách 1:

**CREATE TABLE** _table_name_(<br>
_fk_id_ **INT FOREIGN KEY REFERENCES** _table_pk_(_id_)<br>
);

## Cách 2:

**CREATE TABLE** _table_name_(<br>
_fk_id_ **INT**,<br>
**FOREIGN KEY** _fk_id_ **REFERENCES** _table_pk_(_id_)<br>
);

## Trường hợp: Khi đã tạo bảng, rồi xác định cột nào thành FOREIGN KEY

## Cách 1:

**ALTER TABLE** _table_name_<br>
**ADD FOREIGN KEY** (_fk_id_) **REFERENCES** _table_pk_(_id_);

### Cách 2: CONSTRAINT - đặt tên cho ràng buộc khoá chính

**ALTER TABLE** _table_name_
**ADD CONSTRAINT** _constraint_fk_name_
**FOREIGN KEY** (_fk_id_) **REFERENCES** _table_pk_(_id_);

## Huỷ khoá phụ

**ALTER TABLE** _table_name_ **DROP CONSTRAINT** _constraint_fk_name_;
