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

SELECT SUM(SAL),MAX(SAL),MIN(SAL),AVG(SAL),COUNT(SAL) FROM EMP

http://sql.main.jp/sql06.html

４範囲指定

SELECT ENAME,SAL FROM EMP  WHERE SAL >= 1000 AND SAL <= 2000

http://sql.main.jp/sql07.html

５パターン検索

SELECT ENAME,SAL FROM EMP WHERE ENAME LIKE '%A%' 

http://sql.main.jp/sql08.html

６グループ化（GROUP BY）

SELECT DEPTNO,AVG(SAL) FROM EMP GROUP BY DEPTNO

http://sql.main.jp/sql09.html

７グループ化したテーブルの条件抽出（HAVING）

SELECT DEPTNO,COUNT(*) FROM EMP GROUP BY DEPTNO HAVING COUNT(*) >= 4

SELECT JOB,MIN(SAL),MAX(SAL),AVG(SAL) FROM EMP GROUP BY JOB HAVING MAX(SAL) >= 2000

http://sql.main.jp/sql10.html

８重複行の排除（DISTINCT）

SELECT DISTINCT JOB FROM EMP 

http://sql.main.jp/sql11.html

９レコードの追加 INSERT文

INSERT INTO	EMP (EMPNO,NAME,JOB,MGR,HIREDATE,SAL,COMM,DEPTNO)
VALUES	(9999,'SAN','SALESMAN',7698,1981-09-28,1000,500,10)


INSERT INTO	EMP_TEMP
SELECT	*
FROM	EMP
WHERE	JOB = 'SALESMAN'

http://sql.main.jp/sql12.html

１０レコードの更新 UPDATE文

UPDATE	表名
SET	列名 = 値,列名 = 値...
WHERE	条件

UPDATE	EMP
SET	SAL = SAL * 1.5
WHERE	EMPNO = 7369

http://sql.main.jp/sql13.html

１１レコードの削除 DELETE文

DELETE FROM EMP WHERE EMPNO = 7369

http://sql.main.jp/sql14.html

１２ー１複数表への問い合わせ

SELECT EMP.ENAME,DEPT.DNAME FROM EMP,DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO

SELECT EMP.SAL,DEPT.DNAME FROM EMP,DEPT WHERE SAL >= 1500

１２ー２エイリアス（別名）

SELECT E.ENAME,EDEPTNO,D.DNAME,D.DEPTNO FROM EMP E,DEPT D WHERE E.DEPTNO = D.DEPTNO

http://sql.main.jp/sql15.html

１３入れ子の問合せ

副問い合わせ

SELECT * FROM EMP WHERE EMP.DEPTNO = (SELECT MIN (DEPT.DEPTNO) FROM DEPT

IN記述

SELECT * FROM EMP WHERE DEPTNO NOT IN (10,20)

SELECT * FROM EMP WHERE IN (SELECT DEPTNO FROM DEPT WHERE DNAME LIKE '%S&'

EXIST記述

SELECT ENAME,SAL FROM EMP EA WHERE NOT EXIST (SELECT * FROM EMP EB WHERE EB.SAL > EA.SAL ) 

http://sql.main.jp/sql16.html

