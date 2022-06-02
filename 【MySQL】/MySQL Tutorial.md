# MySQL Tutorial

[TOC]



## Chapter Notes

### 1. Understanding SQL

> This Chapter introduces **some basic SQL terms**



#### 1.1 database

**Q1: What is *==<u>database</u>==*?** 

> ***Database** is a collection of data stored in an organized fashion.*



#### 1.2 table

**Q1: What is ==*<u>table</u>*==?**

> ***table** is structured file that stores data of a specific type.*



#### 1.3 column/row

**Q1: What is *==<u>column/row</u>==*?**

>***column** is a single  field in a table* 
>
>***row** is a single record in a table*



#### 1.4 Primary Key

**Q1: What is *<u>==Primary Key==</u>*?**

> ***Primary Key** is a column or a set of columns whose values uniquely identify every row in a table .*



**Q2: What's the main attributes of values in Primary Key?**

> *1. No **same** value*
>
> *2. No **NULL** value*



**Q3: Can a table have more than one Primary Key?**

> ***No**, one table can only have one primary key.But that key can be a set of columns.*



#### 1.5 SQL 

**Q1: What is the full name of  *<u>==SQL==</u>*?**

> *Structured Query Language*



**Q2: What are the advantages of SQL?**

>1. *SQL is simple enough and easy to learn.*
>2. *SQL is not a proprietary language and has strong portability.*
>3. *SQL is powful and support complex database operations.*



### 2. Working with MySQL

### 3. Retrieving Data

### 4. Sorting Retrieved Data

### 5. Filtering Data



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
> + how to **combine SELECT statements** with the **UNION** operator
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





