# OS

Linux → MacOS

```bash
scp parallels@10.211.55.4:/home/parallels/Desktop/new.c /Users/rickyx/Desktop
```



MacOS → Linux

```
scp /Users/rickyx/Desktop/test.c parallels@10.211.55.4:/home/parallels/Desktop
```

![image-20220610213544478](https://tva1.sinaimg.cn/large/e6c9d24ely1h33h5i3xe6j21u80u07aw.jpg)

![image-20220610213706830](https://tva1.sinaimg.cn/large/e6c9d24ely1h33h6vvvtrj21rc0u0q65.jpg)



![image-20220610215228662](https://tva1.sinaimg.cn/large/e6c9d24ely1h33hmvincej21h00u00zd.jpg)





![image-20220612120354597](https://tva1.sinaimg.cn/large/e6c9d24ely1h35bv4t1fpj21xr0u0q9c.jpg)





![image-20220612121629464](https://tva1.sinaimg.cn/large/e6c9d24ely1h35c86cjnyj22020u044p.jpg)

![image-20220612123312037](https://tva1.sinaimg.cn/large/e6c9d24ely1h35cpki9dzj21ut0u07az.jpg)







![image-20220612130349405](https://tva1.sinaimg.cn/large/e6c9d24ely1h35dlfh2u5j21sz0u0dlq.jpg)





![image-20220612131530796](https://tva1.sinaimg.cn/large/e6c9d24ely1h35dxlcmg0j21rh0u0jzu.jpg)





![image-20220612134301357](https://tva1.sinaimg.cn/large/e6c9d24ely1h35eq7wc8kj21kk0u0q9s.jpg)





![image-20220612135309559](https://tva1.sinaimg.cn/large/e6c9d24ely1h35f0rdmn2j21te0u0tg8.jpg)





## 大题

### 死锁定理

[死锁与资源分配图](https://blog.csdn.net/qq_45812180/article/details/118024236?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165569389516781685354549%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165569389516781685354549&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-118024236-null-null.142^v17^pc_search_result_control_group,157^v15^new_3&utm_term=%E6%AD%BB%E9%94%81%E5%AE%9A%E7%90%86&spm=1018.2226.3001.4187)

> 死锁定理：
>
> 由于该资源图可以完全简化，根据死锁定理，该系统不存在死锁状态
>
> 由于该资源图不可完全简化，根据死锁定理，该系统存在死锁状态，产生死锁的进程为P / P / P

例题：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ej389mh1j20zq0ks0ud.jpg" alt="image-20220620110400969" style="zoom:33%;" />

答案：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ej3hz390j20q00ckjs3.jpg" alt="image-20220620110416445" style="zoom:33%;" />



### 银行家算法

[银行家算法原理](https://qyliang.blog.csdn.net/article/details/80245715?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-80245715-blog-124590305.pc_relevant_antiscanv3&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-80245715-blog-124590305.pc_relevant_antiscanv3&utm_relevant_index=1)

[银行家算法练习题](https://blog.csdn.net/nb_zsy/article/details/104194839?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165569506016782350917014%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=165569506016782350917014&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-104194839-null-null.142^v17^pc_search_result_control_group,157^v15^new_3&utm_term=2.%2810%E5%88%86%EF%BC%89%E6%9F%90%E7%B3%BB%E7%BB%9F%E6%9C%89+R1%E3%80%81R2+%E5%92%8C+R3+%E5%85%B13+%E7%A7%8D%E8%B5%84%E6%BA%90%EF%BC%8C%E5%9C%A8+TO+%E6%97%B6%E5%88%BB%EF%BC%8CP1%E3%80%81P2%E3%80%81P3+%E5%92%8C+P4+%E8%BF%994+%E4%B8%AA%E8%BF%9B%E7%A8%8B%E5%AF%B9%E8%B5%84%E6%BA%90%E7%9A%84%0A%E5%8D%A0%E6%9C%89%E5%92%8C%E9%9C%80%E6%B1%82%E6%83%85%E5%86%B5%E5%A6%82%E4%B8%8B%E8%A1%A8%E6%89%80%E7%A4%BA%EF%BC%8C%E6%AD%A4%E5%88%BB%E7%B3%BB%E7%BB%9F%E5%8F%AF%E7%94%A8%E8%B5%84%E6%BA%90%E5%90%91%E9%87%8F%E4%B8%BA%282%EF%BC%8C1%EF%BC%8C2%EF%BC%89&spm=1018.2226.3001.4187)

例题：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3eja6abtzj211e0g4q52.jpg" alt="image-20220620111041245" style="zoom:50%;" />

答案：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ejfcgox6j210d0u0dkt.jpg" alt="image-20220620111539579" style="zoom:50%;" />

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ek2pxdulj20u00z6dke.jpg" alt="image-20220620113807623" style="zoom: 50%;" />

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ek3ffj4gj20u012bdkq.jpg" alt="image-20220620113848080" style="zoom: 50%;" />



### 平均周转时间/平均带权周转时间

执行时间 = 所有执行的时间之和

周转时间 = 完成时间 - 到达处理机时间

带权周转时间 = 周转时间 / 执行时间

#### 单道程序

例题：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ek5yg18rj210e0man0o.jpg" alt="image-20220620114114314" style="zoom:50%;" />

答案：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ekiy45ktj20si0jgwh7.jpg" alt="image-20220620115343777" style="zoom:50%;" />



#### 多道程序

例题：

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ekq976w8j20zm0oqwjf.jpg" alt="image-20220620120044911" style="zoom:50%;" />

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3ekqldycjj210m0dcgo5.jpg" alt="image-20220620120104510" style="zoom:50%;" />

答案：

![image-20220620120145331](https://tva1.sinaimg.cn/large/e6c9d24ely1h3ekrap7b1j20ts0d2wfe.jpg)