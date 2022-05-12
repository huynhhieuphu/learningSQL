TRANSACTION trong sql

Trường hợp: Khi có nhiều hành động cần xử lý hàng loạt và cần xem xét các hành động đó có hợp lệ hay không? nếu không hợp lệ sẽ không ghi nhận hoặc chỉ ghi nhận tại 1 thời điểm được chỉ định.

- Sử dụng TRANSACTION trong trường hợp quay lại

===================================
=== BEGIN TRANSACTION           ===
===                             ===
=== 	do something...         ===
===                             ===
=== ROLLBACK {TRANSACTION|TRAN} ===
===================================


- Sử dụng TRANSACTION trong trường hợp ghi nhận

=================================
=== BEGIN TRANSACTION         ===
===                           ===
===		do something...       ===
===                           ===
=== COMMIT {TRANSACTION|TRAN} ===
=================================

- Sử dụng TRANSACTION đặt tên

====================================
=== BEGIN TRANSACTION tran_name  ===
===                              ===
===    do something...           ===
===                              ===
=== COMMIT TRANSACTION tran_name ===
====================================

- Sử dụng TRANSACTION trong trường hợp quay lại thời điểm chỉ định

=============================================
=== BEGIN TRANSACTION                     ===
===                                       ===
=== SAVE {TRANSACTION|TRAN} time_1        ===
===                                       ===
===	   do something 1...                  ===
===                                       ===
=== SAVE {TRANSACTION|TRAN} time_2        ===
===                                       ===
=== COMMIT {TRANSACTION|TRAN}             ===
===                                       ===
===	   do something 2...                  ===
===                                       ===
=== ROLLBACK {TRANSACTION|TRAN} time_save ===
=============================================