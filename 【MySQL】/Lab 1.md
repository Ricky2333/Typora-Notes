# Lab 1

## Tables

### emp

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h394o37fvpj21iu0rc47q.jpg" alt="image-20220615185715252" style="zoom:50%;" />

### dept

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h394ngzr4tj20ya0bu0uh.jpg" alt="image-20220615185639636" style="zoom: 50%;" />





## Q1

> **检索所有员工及其相关领导的姓名**

```mysql
select e1.ename as clerk,e2.ename as mgr
from emp as e1,emp as e2
where e1.mgr = e2.empno;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h394jo0cssj20v00u0diq.jpg" alt="image-20220615185300134" style="zoom: 33%;" />

```mysql
select e1.ename as clerk,e2.ename as mgr
from emp as e1 INNER JOIN emp as e2
on e1.mgr = e2.empno;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h394ktjfo0j20vo0u0tbo.jpg" alt="image-20220615185406893" style="zoom:33%;" />

## Q2

> **查询聘用日期早于他们的领导的雇员姓名**

```mysql
select e1.ename as clerk,e2.ename as mgr
from emp as e1,emp as e2
where e1.mgr = e2.empno and e1.hiredate < e2.hiredate;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h394jo0cssj20v00u0diq.jpg" alt="image-20220615185300134" style="zoom: 33%;" />



## Q3

> **检索所有员工姓名的前三个字母；**

```mysql
select left(ename,3) from emp;
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h395ljt1tfj20ni0i6aaw.jpg" alt="image-20220615192924739" style="zoom:50%;" />



## Q4

> **检索1号部门所有员工的人数和平均年薪；**

```mysql
select count(*) as num,avg((sal+comm)*12) as avg
from emp
where deptno=1;
```

![image-20220615193859408](https://tva1.sinaimg.cn/large/e6c9d24ely1h395vihlm2j20yo0cct9y.jpg)





## Q5

> **检索每个部门的名称和人数。**

```mysql
select dname,count(*) as num
from dept,emp
where emp.deptno=dept.deptno
group by emp.deptno;
```

![image-20220615194746303](https://tva1.sinaimg.cn/large/e6c9d24ely1h3964n903lj20zs0hign6.jpg)



## Q6

> **检索每一种工作的最低工资和相应的工作。**

```mysql
select job,min(sal) as min_sal
from emp
group by job;
```

![image-20220615195031438](https://tva1.sinaimg.cn/large/e6c9d24ely1h3967impf5j20sm0kytaf.jpg)





## Q7

>  **查询各个部门经理职位（manager）的员工最低工资。**

```mysql
select dname,min(sal) as min_sal
from dept,emp
where job='manager' and dept.deptno=emp.deptno
group by emp.deptno;
```

![image-20220615195815639](https://tva1.sinaimg.cn/large/e6c9d24ely1h396fkiu8pj20xu0eo0um.jpg)











## Q8

> 检索1号部门所有员工的人数和平均年薪；

```mysql

```



## Q9

> 检索1号部门所有员工的人数和平均年薪；

```mysql

```



## Q10

> **检索所有部门名称和所有员工，包括那些没有任何员工的部门。**

```mysql
select dname,ename
from dept left outer join emp
on dept.deptno=emp.deptno;
```

![image-20220615200824112](https://tva1.sinaimg.cn/large/e6c9d24ely1h396q5v6coj20u00ws77q.jpg)

