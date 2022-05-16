# Kiểu dữ liệu

**INT** : số nguyên VD: -1; 0; 20; 99;...<br>
**FLOAT** : số thực, số tập phân VD: 1.4; 9,5;<br><br>

**CHAR** : chuỗi -> Bộ nhớ cấp phát cứng -> chỉ định bao nhiêu thì sử dụng bấy nhiêu<br>
**NCHAR** : chuỗi -> Bộ nhớ cấp phát cứng (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)<br>
**VARCHAR** : chuỗi -> Bộ nhớ cấp phát động -> dùng bao nhiêu thì cấp phát dùng đúng bấy nhiêu<br>
**NVARCHAR** : chuỗi -> Bộ nhớ cấp phát động (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)<br>
**TEXT** : lưu văn bản lớn<br>
**NTEXT** : lưu văn bản lớn (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)<br><br>

**DATE** : năm-tháng-ngày YYYY-MM-DD<br>
**TIME** : giờ:phút:giây HH:MI:SS<br>
**DATETIME** : năm-tháng-ngày giờ:phút:giây<br><br>

**BOOLEAN** : lưu giá trị 0 và 1<br>
**BIT** : lưu giá trị 0, 1 hoặc NULL<br><br>

**ENUM** : Lưu giá trị theo dạng select. vd ENUM('male','female','Other')<br><br>

_Lưu ý_: NCHAR, NVARCHAR, NTEXT -> khi gõ unicode -> cần có N'text'<br><br>

[Tham Thảo: CÁC KIỂU DATA TYPES TRONG MYSQL ](https://viblo.asia/p/cac-kieu-data-types-trong-mysql-eW65G42PKDO#_31-kieu-du-lieu-char-va-varchar-10)<br><br>

**_Sự khác nhau giá trị: empty, null, undefined_**<br><br>

_TH: một ly nước_<br><br>

_- empty : không còn giọt nước trong ly nước_<br>
_- null : Ly nước chưa từng được đổ nước vào ly_<br>
_- undefined : không có luôn ly nước, chưa từng được_<br><br>

Một số hàm thường sử dụng<br><br>

**CURDATE**() : trả về ngày tháng hiện tại (của mysql)<br>
**DAY**('1987-08-10') : trả về ngày. vd: ngày 10<br>
**MONTH**('1987-08-10') : trả về tháng. vd: tháng 8<br>
**YEAR**('1987-08-10') : trả về năm. vd: tháng 1987<br><br>

**CAT()** : chuyển đổi giá trị thành kiểu định dạng chỉ định<br><br>

SELECT CAST('2022-05-16 21:45:43' AS DATE);

> 2022-05-16

SELECT CAST('2022-05-16 21:45:43' AS TIME);

> 21:45:09
