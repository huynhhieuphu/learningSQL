# GROUP BY - HAVING

**SELECT** _column_name(s)_<br>
**FROM** _table_name_<br>
**WHERE** _condition_<br>
**GROUP BY** _column_name(s)_<br>
**HAVING** _condition_<br>
**ORDER BY** \_column_name(s);

_Lưu ý:_

- Lệnh WHERE không được dùng cho Aggregate Funcion
- HAVING -> giống như WHERE nhưng dành cho GROUP BY
- HAVING là lệnh điều kiện của GROUP BY
- HAVING chỉ dùng cho Agreeate function hoặc các cột của GROUP BY

  Ví dụ: Đếm tất cả sản phẩm đã bán dưới 10 cái

  ===============================================================================================
  === SELECT p.name, COUNT(od.id) AS selled FROM Products AS p INNER JOIN Order_Details AS od ===
  === ON p.id = od.product_id ===
  === GROUP BY p.name ===
  === HAVING COUNT(od.id) < 10; ===
  ===============================================================================================
