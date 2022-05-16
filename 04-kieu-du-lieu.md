# Kiểu dữ liệu

**INT** : số nguyên VD: -1; 0; 20; 99;...
**FLOAT** : số thực, số tập phân VD: 1.4; 9,5;

**CHAR** : chuỗi -> Bộ nhớ cấp phát cứng -> chỉ định bao nhiêu thì sử dụng bấy nhiêu
**NCHAR** : chuỗi -> Bộ nhớ cấp phát cứng (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)
**VARCHAR** : chuỗi -> Bộ nhớ cấp phát động -> dùng bao nhiêu thì cấp phát dùng đúng bấy nhiêu
**NVARCHAR** : chuỗi -> Bộ nhớ cấp phát động (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)
**TEXT** : lưu văn bản lớn
**NTEXT** : lưu văn bản lớn (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)

**DATE** : năm-tháng-ngày YYYY-MM-DD
**TIME** : giờ:phút:giây HH:MI:SS
**DATETIME** : năm-tháng-ngày giờ:phút:giây

**BOOLEAN** : lưu giá trị 0 và 1
**BIT** : lưu giá trị 0, 1 hoặc NULL

**ENUM** : Lưu giá trị theo dạng select. vd ENUM('male','female','Other')

_Lưu ý_: NCHAR, NVARCHAR, NTEXT -> khi gõ unicode -> cần có N'text'

[Tham Thảo: CÁC KIỂU DATA TYPES TRONG MYSQL ](https://viblo.asia/p/cac-kieu-data-types-trong-mysql-eW65G42PKDO#_31-kieu-du-lieu-char-va-varchar-10)

**_Sự khác nhau giá trị: empty, null, undefined_**

_TH: một ly nước_

_- empty : không còn giọt nước trong ly nước_
_- null : Ly nước chưa từng được đổ nước vào ly_
_- undefined : không có luôn ly nước, chưa từng được_

Một số hàm thường sử dụng

**CURDATE**() : trả về ngày tháng hiện tại (của mysql)
**DAY**('1987-08-10') : trả về ngày. vd: ngày 10
**MONTH**('1987-08-10') : trả về tháng. vd: tháng 8
**YEAR**('1987-08-10') : trả về năm. vd: tháng 1987

**CAT()** : chuyển đổi giá trị thành kiểu định dạng chỉ định

SELECT CAST('2022-05-16 21:45:43' AS DATE);<br>

> 2022-05-16 <br>

SELECT CAST('2022-05-16 21:45:43' AS TIME);<br>

> 21:45:09
