AUTO INCREMENT

CREATE TABLE table_name (
	id INT IDENTIY(1,1) PRIMARY KEY,
	column_name ...,
)

	IDENTITY hàm tự tăng mỗi khi insert
	- tham số 1 là số bắt đầu, ví dụ: bắt đầu từ số 1
	- tham số 2 là đơn vị tăng, ví dụ: mỗi lần tăng 1 đơn vị

MYSQL

CREATE TABLE table_name (
	id INT NOT NULL AUTO_INCREMENT,
	column_name data_type ...,
	column_name data_type ...,
	...
	PRIMARY KEY(id)
)

	AUTO_INCREMENT hàm tự tăng khi insert của MYSQL
	- Chỉ có 1 tham số số bắt đầu, ví dụ: bắt đầu tăng từ số 100 