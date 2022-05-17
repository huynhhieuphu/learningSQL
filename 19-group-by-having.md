# GROUP BY - HAVING

**SELECT** _column_name(s)_<br>
**FROM** _table_name_<br>
**WHERE** _condition_<br>
**GROUP BY** _column_name(s)_<br>
**HAVING** _condition_<br>
**ORDER BY** _column_name(s)_;<br><br>

_Lưu ý:_<br>

- Lệnh WHERE không được dùng cho Aggregate Funcion<br>
- HAVING -> giống như WHERE nhưng dành cho GROUP BY<br>
- HAVING là lệnh điều kiện của GROUP BY<br>
- HAVING chỉ dùng cho Agreeate function hoặc các cột của GROUP BY<br><br>

_Ví dụ: Đếm tất cả sản phẩm đã bán dưới 10 cái_
SELECT p.name, COUNT(od.id) AS selled<br>
FROM Products AS p<br>
INNER JOIN Order_Details AS od<br>
ON p.id = od.product_id<br>
GROUP BY p.name<br>
HAVING COUNT(od.id) < 10;
