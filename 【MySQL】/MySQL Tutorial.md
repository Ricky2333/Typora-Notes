# MySQL Learning Notes

[TOC]

### 1. SQL Basics

#### Summary

> This Chapter introduces:
>
> + some **basic SQL terms**



#### Contents

##### **Q1: What is *==<u>database</u>==*?** 

> ***Database** is a collection of data stored in an organized fashion.*



##### **Q2: What is ==*<u>table</u>*==?**

> ***table** is structured file that stores data of a specific type.*



##### **Q3: What is *==<u>column/row</u>==*?**

>***column** is a single  field in a table* 
>
>***row** is a single record in a table*



##### **Q4: What is *<u>==Primary Key==</u>*?**

> ***Primary Key** is a column or a set of columns whose values uniquely identify every row in a table .*



##### **Q5: What's the main attributes of values in Primary Key?**

> *1. No **identical** values*
>
> *2. No **NULL** value*



##### **Q6: Can a table have more than one Primary Key?**

> ***No**, one table can only have one primary key.But that key can be a set of columns.*



##### **Q7: What is the full name of  *<u>==SQL==</u>*? **What are the advantages of SQL?

> *Structured Query Language*

>1. *SQL is **simple enough** and easy to learn.*
>2. *SQL is not a proprietary language and has **strong portability**.*
>3. *SQL is **powful** and support complex database operations.*



##### **Q9: What is ==MySQL==?**

> *MySQL is a **Database Management System** (DBMS)*





### 2. Working with MySQL

#### Summary

> This Chapter introduces:
>
> + how to **log in** MySQL
> + how to **show** Databases & Tables by using  **`SHOW`**
> + how to **select** current Databases by using **`USE`**



#### Contents

##### 1. Log in MySQL

> + ***hostname***
> + ***The port** (if a port other than the default 3306 is used)*
> + *a valid **user name***
> + *The user **password** (if required)*

```mysql
mysql -u root -p
```

![image-20220614151052916](https://tva1.sinaimg.cn/large/e6c9d24ely1h37sia9ryuj21ce0kcdjt.jpg)



##### 2. Show current Databases & Tables

```mysql
show databases;
show tables;
```

![image-20220614151633913](https://tva1.sinaimg.cn/large/e6c9d24ely1h37so5vs9rj21480lkjur.jpg)



##### 3. Select Databases

```mysql
use [Database_name]
```

![image-20220614152203542](https://tva1.sinaimg.cn/large/e6c9d24ely1h37stvfp7ij21gi0ck77c.jpg)





### 3. Retrieving Data

#### Summary

> This Chapter introduces:
>
> + how to **retrieve data** by using **`SELECT`** & `wildcards '*'`
> + how to **retrieve distinct data** by using **`DISTINCT`**
> + how to **limit the amount of retrieved data** by using **`LIMIT`**



#### Contents

##### 1. retrieve specified columns 

```mysql
select ename,sal
from emp;
```

![image-20220614153443210](https://tva1.sinaimg.cn/large/e6c9d24ely1h37t71nng1j20gs0d0dgq.jpg)

##### 2. retrieve all columns 

```mysql
select * from emp;   #by using wildcards '*'
```

![image-20220614153706199](https://tva1.sinaimg.cn/large/e6c9d24ely1h37t9j2y5pj21h40d6dk3.jpg)



##### 3. retrieve distinct data

```mysql
select DISTINCT sal
from emp;
```

![image-20220614160148474](https://tva1.sinaimg.cn/large/e6c9d24ely1h37tz8eqktj21je0ky0vn.jpg)



**Wrong Syntax**

![image-20220614160529695](https://tva1.sinaimg.cn/large/e6c9d24ely1h37u32fi0rj21m408ggoe.jpg)

![image-20220614160310150](https://tva1.sinaimg.cn/large/e6c9d24ely1h37u0ndsv2j21x00gydkh.jpg)



##### 4. retrieve data with limit

**`LIMIT [startrow_num],[amount]`**

```mysql
select ename,sal 
from emp
LIMIT 0,3;   #start from row0,retrieve 3 rows
```

![image-20220614162453067](https://tva1.sinaimg.cn/large/e6c9d24ely1h37un8p9djj214y0eymz8.jpg)



### 4. Sorting Retrieved Data

#### Summary

> This Chapter introduces:
>
> + how to **sort retrieved data** by using **`ORDER BY `** clause
> + how to **retrieve the maximum & minimum** row by using  **`ORDER BY & LIMIT`**



#### Contents

##### 1. Ascending Sort

**`ORDER BY [Field_name]`**

```mysql
select ename,sal,comm
from emp
order by sal,comm;
```

![image-20220614170837090](https://tva1.sinaimg.cn/large/e6c9d24ely1h37vwqkof2j214i0ko783.jpg)



##### 2. Descending Sort 

**`ORDER BY [Field_name] DESC`**

```mysql
select ename,sal,comm
from emp
order by sal,comm DESC;
```

![image-20220614171151820](https://tva1.sinaimg.cn/large/e6c9d24ely1h37w048ak3j216a0m6429.jpg)



##### 3. Retrieve maximun &minimum

**`ORDER BY [Field_name]`**

**`LIMIT 1`**

```mysql
select ename,sal,comm
from emp
order by sal DESC
LIMIT 1;
```

![image-20220614171814754](https://tva1.sinaimg.cn/large/e6c9d24ely1h37w6rga87j20vg0do40a.jpg)





### 5. Filtering Data

#### Summary

> This Chapter introduces:
>
> + how to **filter data** by using  **`where`** clause.
> + how to **check for nonmatches** by using **`<>`**
> + how to **check for a range of values** by using  **`BETWEEN AND`**
> + how to **check for NULL values** by using  **`IS NULL`**
> + how to **check for discrete values** by using  **`IN (Value1,Value2)`**



#### Contents

##### 1. Checking for Nonmatches

**`WHERE [Field_name] <> [values]`**

```mysql
select empno,ename,sal,comm
from emp
where sal <> 1111;
```

![image-20220614184625663](https://tva1.sinaimg.cn/large/e6c9d24ely1h37yqihdpjj20wq0eigne.jpg)



##### 2. Checking for a Range of Values

**`WHERE [Field_name] BETWEEN [value1] AND [value2]`**

```mysql
select empno,ename,sal,comm
from emp
where sal BETWEEN 1000 AND 2000;
```

![image-20220614184919407](https://tva1.sinaimg.cn/large/e6c9d24ely1h37ytiv9gjj20xs0eyq53.jpg)



##### 3. Checking for NULL Values

**`WHERE [Field_name] IS NULL`**

```mysql
select empno,ename,job,mgr,sal,comm
from emp
where mgr IS NULL;
```

![image-20220614185723685](https://tva1.sinaimg.cn/large/e6c9d24ely1h37z1xdi9qj213u0lqaed.jpg)



##### 4. Checking for Discrete Values

**`WHERE [Field_name] IN (Value1,Value2,Value3)`**

```mysql
select empno,ename,job,mgr,sal,comm
from emp
where job IN ('Manager','Salesman');
```

![image-20220614190555972](https://tva1.sinaimg.cn/large/e6c9d24ely1h37zasy9mvj211i0pegr4.jpg)





### 6. Searching Using Regular Expression

#### Summary

> This Chapter introduces:
>
> + what is **Calculated Fields** and how to create them
>
> + the use of calculated fields for both **string concatenation** and **mathematical operations.**
>
> + how to create and use **aliases** so your application can refer to calculated fields.
>
> Key words:
>
> + **Concat( )**
> + **AS**
> + **TRIM( )**



#### Contents

##### 1. string concatenation

```mysql
select Concat(TRIM(ename),'\'s Job is ',TRIM(job))
from emp;
```

![image-20220524212710478](https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtdc4s8kj20z80e240o.jpg)



##### 2. mathematical operations

```mysql
select Concat(TRIM(ename),'\'s annual salary is ',sal*12)
from emp;
```

![image-20220524212836151](https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtesdy0tj213m0fa77d.jpg)



##### 3. aliases

```mysql
select salary*12 AS annual_salary 
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtifvz36j20p20bc0tg.jpg" alt="image-20220524213207263" style="zoom:67%;" />





### 7. Creating Calculated Fields

#### Summary

> This Chapter introduces:
>
> + what is **Calculated Fields** and how to create them
>
> + the use of calculated fields for both **string concatenation** and **mathematical operations.**
>
> + how to create and use **aliases** so your application can refer to calculated fields.
>
> Key words:
>
> + **Concat( )**
> + **AS**
> + **TRIM( )**

 

#### Contents

##### 1. string concatenation

```mysql
select Concat(TRIM(ename),'\'s Job is ',TRIM(job))
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtdc4s8kj20z80e240o.jpg" alt="image-20220524212710478" style="zoom:67%;" />



##### 2. mathematical operations

```mysql
select Concat(TRIM(ename),'\'s annual salary is ',sal*12)
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtesdy0tj213m0fa77d.jpg" alt="image-20220524212836151" style="zoom:67%;" />



##### 3. aliases

```mysql
select salary*12 AS annual_salary 
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtifvz36j20p20bc0tg.jpg" alt="image-20220524213207263" style="zoom:67%;" />





### 8. Using Functions

#### Summary

> This Chapter introduces:
>
> + how to use **SQL’s data manipulation functions**
> + how to use **SQL’s aggregate functions** to summarize data
>
> Key words:
>
> + **Text-Manipulation** Functions
> + **Numeric **Functions
> + **Date and Time** Functions
> + **System** Functions
> + **DISTINCT**



#### Contents

##### 1. Text-Manipulation Functions

![image-20220524213935424](https://tva1.sinaimg.cn/large/e6c9d24ely1h2jtq80nhcj216o0titd8.jpg)

```mysql
select left(ename,1) as First
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjketxlbj20mw0guwf6.jpg" alt="image-20220525123335157" style="zoom: 67%;" />



##### 2. Numeric Functions

![image-20220525123059941](https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjhptc1aj211y0o0gpj.jpg)

```mysql
select sqrt(sal) as new_sal
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjn1sdl4j20lk0d2q4b.jpg" alt="image-20220525123607363" style="zoom:67%;" />



##### 3. Date and Time Functions

![image-20220525123038892](https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjhcz7g2j20u00wdjw1.jpg)

```mysql
select * from emp
where Year(hiredate)='2013' AND Month(hiredate)='5';
```

![image-20220525123816533](https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjpaf6uej21gc0b8gp3.jpg)



##### 4. Aggregate Functions

![image-20220525124510600](https://tva1.sinaimg.cn/large/e6c9d24ely1h2kjwgvfutj21k00m4gpe.jpg)

```mysql
select Avg(sal) as avg_sal,
			 Avg(Distinct sal) as avg_dis_sal,
			 Max(sal) as max_sal,
			 Min(sal) as min_sal,
			 Count(sal) as cnt_sal
from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2kruh83ddj218w0gcdiv.jpg" alt="image-20220525172002929" style="zoom: 50%;" />

```mysql
select COUNT(*) from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2kllw6r22j20ka09uq3g.jpg" alt="image-20220525134412373" style="zoom:67%;" />

```mysql
select COUNT(mgr) from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2klng2ou4j20yc0u0qas.jpg" alt="image-20220525134541969" style="zoom: 67%;" />



### 9. Grouping data

#### Summary

> This Chapter introduces:
>
> + how to use the **GROUP BY clause** to perform calculations on groups of data, returning results for each group
> + how to use the **HAVING clause** to filter specific groups
> + the **difference between ORDER BY and GROUP BY** and **between WHERE and HAVING**
> + conclusion of **SELECT clause Order**



#### Contents

##### 1. Group BY

🟢 **Right Syntax**

```mysql
select job,COUNT(*) as num
from emp
group by job;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2m6zfrwwsj20mc0i2jst.jpg" alt="image-20220526224921747" style="zoom: 67%;" />

🔴 **Wrong Syntax** 

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2m7i4zejcj21060b00w0.jpg" alt="image-20220526230720831" style="zoom:67%;" />



##### 2. Having 

🟢 **Right Syntax**

```mysql
select job,avg(sal) as avg_sal
from emp
group by job
having avg_sal>3000;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2m79zh9wvj20uu0u00ws.jpg" alt="image-20220526225930661" style="zoom: 67%;" />

🔴 **Wrong Syntax** 

![image-20220526230945713](https://tva1.sinaimg.cn/large/e6c9d24ely1h2m7knr8zrj212i070abx.jpg)



##### 3. WHERE VS HAVING

+ WHERE filters **rows**  &  HAVING filters **groups**

+ WHERE filters **before** data is grouped  &  HAVING filters **after** data is grouped 

**A mixture example**

```mysql
select job,avg(sal) as avg_sal
from emp
where comm>300
group by job
having avg_sal>1500;
```

![image-20220529160945716](https://tva1.sinaimg.cn/large/e6c9d24ely1h2pcalzoqqj21by0ioq7i.jpg)



##### 4. ORDER BY VS GROUP BY 

![image-20220529161430800](https://tva1.sinaimg.cn/large/e6c9d24ely1h2pcfimtj9j216e0k6adh.jpg)

**A mixture example**

```mysql
select job,avg(sal) as avg_sal
from emp
where comm>300
group by job
having avg_sal>1500
order by avg_sal;
```

![image-20220529161740604](https://tva1.sinaimg.cn/large/e6c9d24ely1h2pcit08quj21160k876o.jpg)



##### 5.SELECT clause order

![image-20220529162155277](https://tva1.sinaimg.cn/large/e6c9d24ely1h2pcn8bfbxj216k0qoq6l.jpg)



### 10. Joins

#### Summary

> This Chapter introduces:
>
> + how and why to **use aliases for tables**
> + some of the basics of **relational database design** as an introduction to learning about joins
> + how to create an **inner join**
> + how to create an **left/right outer join**



#### Contents

##### 1.Aliases for tables

```mysql
select s_name,class_id
from stu_info as s, c_info as c
where s.s_name = "Ricky" and c.class_id = 3;
```



##### 2. Basic of relational databases

###### 1) What is relational databases?

![image-20220601134646072](https://tva1.sinaimg.cn/large/e6c9d24ely1h2sp0prw4wj21bn0u0q6b.jpg)

> + each relational tables contains one specific type of data
> + relational tables are joined by Primary Key & Foreign Key



###### 2) What's the merits of using relational databases?

> + more clear **on logic**
> + **space-efficient** (decrease the repetition )
> + **more consistent and secure** when modification happens

![image-20220601133955771](https://tva1.sinaimg.cn/large/e6c9d24ely1h2sotlm7fmj21e80e0761.jpg)

![image-20220601133914526](https://tva1.sinaimg.cn/large/e6c9d24ely1h2sosvsvnkj21by0h2myu.jpg)



##### 3. Joins

###### Sample Table

+ **Suppose** we have 2 tables, one is `Students` and another is `Class`

![image-20220531182739940](https://tva1.sinaimg.cn/large/e6c9d24ely1h2rrioqkkjj219q0k00ui.jpg)

+ Now we want to **retrieve data** which are combined by these two tables. 



There are **4 basic situations**

###### 1) No Joins

```mysql
select s_name,class_id,class_floor
from Students as s,Class as c;
```

![image-20220531185009805](https://tva1.sinaimg.cn/large/e6c9d24ely1h2rs63ei99j21jg0u00w3.jpg)

######  2) Inner Joins

```mysql
select s_name,class_id,class_floor
from Students as s INNER JOIN Class as c
ON s.class_id = c.class_id;
```

![image-20220531185156330](https://tva1.sinaimg.cn/large/e6c9d24ely1h2rs7xn5jdj21pq0feq4i.jpg)**Inner joins** can also **be implemented by where clause**

```mysql
select s_name,class_id,class_floor
from Students as s,Class as c
where s.class_id = c.class_id;
```



######  3) Left Outer Joins

```mysql
select s_name,class_id,class_floor
from Students as s LEFT Outer JOIN Class as c
ON s.class_id = c.class_id
```

![image-20220531185715133](https://tva1.sinaimg.cn/large/e6c9d24ely1h2rsdgq2kwj21pm0jq40n.jpg)

###### 4) Right Outer Joins

```mysql
select s_name,class_id,class_floor
from Students as s RIGHT Outer JOIN Class as c
ON s.class_id = c.class_id
```

![image-20220531185920947](https://tva1.sinaimg.cn/large/e6c9d24ely1h2rsfng33wj21oi0hiq4v.jpg)



### 11.Union

#### Summary

> This Chapter introduces:
>
> + how to **combine SELECT statements** with **`UNION`** 
>
> + how to implement **UNION excluding duplicates** 
> + how to implement **UNION including duplicates**



#### Contents

###### 1.Union excluding duplicates

`WHERE` &  `OR`

```mysql
select ename,job,dname
from emp as e INNER JOIN dept as d
on e.deptno = d.deptno
where (sal > 3000 or comm > 300);
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2svit9ndrj20t40lmdil.jpg" alt="image-20220601173145164" style="zoom:50%;" />

`Union`

```mysql
select ename,job,dname
from emp as e INNER JOIN dept as d
on e.deptno = d.deptno
where sal >3000 
Union 
select ename,job,dname
from emp as e INNER JOIN dept as d
on e.deptno = d.deptno
where comm > 300
order by dname desc;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2svjdwgpbj20so0laq5p.jpg" alt="image-20220601173218600" style="zoom:50%;" />



###### 2.Union including duplicates

`Union ALL`

```mysql
select ename,job,dname
from emp as e INNER JOIN dept as d
on e.deptno = d.deptno
where sal > 3000
Union ALL
select ename,job,dname
from emp as e INNER JOIN dept as d
on e.deptno = d.deptno
where comm > 300
order by dname desc;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2svlvt2mxj20zu0pcafe.jpg" alt="image-20220601173442194" style="zoom:50%;" />



### 12. Insert / Delete / Update

#### Summary

> This Chapter introduces:
>
> + how to **insert new rows** with **`INSERT INTO - Values `** 
> + how to **delete rows** with **`DELETE FROM - WHERE  `** 
> + how to **update rows** with **`UPDATE - SET - WHERE`**



#### Contents

##### 1. Inserting New Rows

###### 1.1 right syntax (with high security)

```mysql
Insert into emp(empno,ename,job)
				 values(100,'Harry','Wizard'),
				       (101,'Ron','Student'),
				       (102,'Hermione','Minister');
```

![image-20220610143709051](https://tva1.sinaimg.cn/large/e6c9d24ely1h3351wu6ugj21gw070ac7.jpg)



###### 1.2 **wrong syntax** (with low security)

```mysql
Insert into emp
values(100,'Harry','Wizard'),
      (101,'Ron','Student'),
      (102,'Hermione','Minister');
```

![image-20220610144628264](https://tva1.sinaimg.cn/large/e6c9d24ely1h335blxrd1j216406stan.jpg)

> order problem



##### 2. Deleting Rows

```mysql
Delete from emp
where empno >= 100;
```

![image-20220610143840419](https://tva1.sinaimg.cn/large/e6c9d24ely1h3353hzpq6j21hc03awex.jpg)



##### 3. Updating Rows

```mysql
Update emp
Set empno=100,ename='helen',job='teacher'
where empno=27;
```

![image-20220610143312400](https://tva1.sinaimg.cn/large/e6c9d24ely1h334xsy6w0j21ha07gq4x.jpg)

![image-20220610143953128](https://tva1.sinaimg.cn/large/e6c9d24ely1h3354qx790j21h405i75x.jpg)





create table

```mysql
create table students
(
	snum   int       NOT NULL AUTO_INCREMENT,
	sname  char(20)  NOT NULL,
	cid    int       NOT NULL,
	PRIMARY KEY(snum)
);
```



![image-20220610151756008](https://tva1.sinaimg.cn/large/e6c9d24ely1h3368c8ofgj20t40cajsa.jpg)



















