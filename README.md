# SQL-study

１SELECT WHERE を使う

SELECT ENAME FROM EMP
WHERE DEPTNO = 20

SELECT ENAME FROM EMP
WHERE JOB = 'CLERK' OR 'SALESMAN'

http://sql.main.jp/sql04.html

２ソート（ORDER BY)の記述

SELECT ENAME,JOB,SAL FROM EMP ORDER BY SAL 

３集合関数

#SUM	引数の総和を求める。NULLの場合は集計対象外
#MAX	引数の最大値を求める。
#MIN	引数の最小値を求める。
#AVG	引数の平均値を求める。NULLの場合は集計対象外。
#COUNT	引数の値の総数を求める。NULLの場合は集計対象外。COUNT(*)と記載可。




