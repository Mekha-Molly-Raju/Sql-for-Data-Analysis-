# Sql-for-Data-Analysis-
Sql queries for data analysis

SELECT Name,Places FROM batch1 WHERE Places='Tamilnadu' ORDER BY Name ASC;
SELECT Name,COUNT(*) AS Age FROM batch1 GROUP BY Name ORDER BY Age DESC;
SELECT batch2.sl_no,batch1.Name AS course,batch2.Fee from batch2 INNER JOIN batch1 ON batch2.sl_no=batch1.sl_no WHERE batch2.Fee>50000 ORDER BY batch2.Fee DESC;
SELECT batch1.Name,batch2.course,batch2.Fee FROM batch1 LEFT JOIN batch2 ON batch1.sl_no=batch2.sl_no ORDER BY batch1.Name;
SELECT batch2.sl_no,batch1.Name,batch2.Fee FROM batch2 RIGHT JOIN batch1 ON batch2.sl_no=batch1.sl_no
SELECT Name FROM batch1 WHERE sl_no IN(SELECT sl_no FROM batch2 WHERE Fee>50000);
SELECT AVG(Fee) AS average_order_value FROM batch2;
CREATE VIEW batch1batch2summary AS SELECT batch1.sl_no,batch1.Name,COUNT(batch2.sl_no)AS total_number,SUM(batch2.Fee)AS total_fee, AVG(batch2.Fee)ASavg_fee_value FROM batch1 LEFT JOIN batch2 ON batch1.sl_no=batch2.sl_no GROUP BY batch1.sl_no,batch1.Name;
