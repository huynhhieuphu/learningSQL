***Kiểu dữ liệu***

- INT 		: số nguyên VD: -1; 0; 20; 99;...
- FLOAT 	: số thực, số tập phân VD: 1.4; 9,5;

- CHAR		: chuỗi -> Bộ nhớ cấp phát cứng -> chỉ định bao nhiêu thì sử dụng bấy nhiêu
- NCHAR		: chuỗi -> Bộ nhớ cấp phát cứng (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)
- VARCHAR	: chuỗi -> Bộ nhớ cấp phát động -> dùng bao nhiêu thì cấp phát dùng đúng bấy nhiêu
- NVARCHAR	: chuỗi -> Bộ nhớ cấp phát động (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)
- TEXT		: lưu văn bản lớn
- NTEXT		: lưu văn bản lớn (cho phép gõ UNICODE -> dấu cũng tính bộ nhớ)

- DATE		: năm-tháng-ngày YYYY-MM-DD
- TIME		: giờ:phút:giây HH:MI:SS
- DATETIME	: năm-tháng-ngày giờ:phút:giây

- BOOLEAN   : lưu giá trị 0 và 1
- BIT		: lưu giá trị 0, 1 hoặc NULL
 
-- Lưu ý: NCHAR, NVARCHAR, NTEXT -> khi gõ unicode -> cần có N'text'

https://viblo.asia/p/cac-kieu-data-types-trong-mysql-eW65G42PKDO#_31-kieu-du-lieu-char-va-varchar-10



Sự khác nhau giá trị:  empty, null, undefined

TH: một ly nước
- empty      : không còn giọt nước trong ly nước
- null       : Ly nước chưa từng được đổ nước vào ly
- undefined  : không có luôn ly nước, chưa từng được


Một số hàm thường sử dụng

CURDATE() 				: trả về ngày tháng hiện tại
DAY('1987-08-10')	    : trả về ngày. vd: ngày 10
MONTH('1987-08-10')		: trả về tháng. vd: tháng 8
YEAR('1987-08-10')		: trả về năm. vd: tháng 1987