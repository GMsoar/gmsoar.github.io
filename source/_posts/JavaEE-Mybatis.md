---
title: JavaEE-Mybatis
date: 2019-08-12 21:03:58
tags: [Java,框架,MyBatis]
categories: MyBatis
---


## 一.MyBatis本质：

        就是代理模式体现。MyBatis作者思想认为JDBC开发流程中所有的步骤
        都是次要业务，认为SQL编写主要任务。开发人员专注于SQL编写应该
        忽略JDBC开发流程，轻度体现ORM思想。

## 二.MyBatis与Hibernate比较

    1.Hibernate：杜绝开发人员亲自使用JDBC,杜绝亲自试用sql命令
                  Hibernate无法SQL优化
                  Hiberante缓存依赖程度过大，一级缓存如何同步二级缓存

    2.MyBatis：杜绝开发人员亲自使用JDBC，认为开发人员专注于sql优化
               MyBatis对于缓存依赖非常轻


## 三.如何看框架源码：

    1.框架都是对某一个老技术的封装。因此看框架之前需要对封装的老技术
      开发流程牢记于心

    2.框架内部某一个类的时候，一定要观察类的继承关系

## 四.JDBC流程
```java
    Class.forName("com.mysql.jdbc.Driver");
    Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/kkb","root","123")
    con.setAutoCommit(false)
    PreparedStatement ps = con.preparedStatement(sql);

    ps.setInt();
    ps.setString();

    try{
        int num=  ps.executeUpdate();DML
        ResultSet rs=   ps.executeQuery(); DQL
        ps.executeBatch();
        con.commit();
    }catch(SQLException ex){
        con.rollback();

   }
    con.close();
    ps.close()

    map("insert into xxxx",ps1)


   String xPath ="//bean"
   String xPath ="//@name"
```

 ## 五.Executor(执行器)：
    1.【基本介绍】
        每一个SqlSession对象都会被分配一个【执行器对象】。
       【执行器对象】主要负责【Connection获取】和【Statement对象管理方案】

    2.【Statement对象管理方案】
        1）简单管理方案：一个Statement接口对象只执行一次。执行完毕就
            Statement接口对象进行销毁
        2）可重用方案： 使用一个Map集合，关键字就是一条Sql语句。对应内容Statement接口对象,等到SqlSession再次接收到相同命令时，就从map集合找到对应Statement接口使用map.put("select * from order", Statement1)
        3）批处理管理方案：将多个Statement包含的SQL语句，交给一个Statement对象输送到数据库，形成批处理操作

    3.执行器继承关系

        1）Executor接口有两个实现类：
                      BaseExecutor
                      CachingExecutor

              2) BaseExecutor:抽象类；减轻Executor接口实现难度。
              3）CachingExecutour:提高查询效率，在查询时首先到缓存中寻找对应的数据。
                                  如果有直接返回，MyBatis框架默认情况下使用执行器缓存执行器
                                  如果缓存执行器没有得到对应结果时，才会交给其他的执行器执行
                                  
      


 ## 六.StatementHandler接口

       1.介绍：

              主要负责【Statement或则PreparedStatment或则CallableStatment】创建工作
              同时负责【PreparedStatment或则CallableStatment】运输的SQL语句中占位符
              赋值任务。此外负责数据库操作对象的运行行为【update】和【query】

      2.关注方法：4个

              1 prepare: 创建Statement对象或则PreparedStatment或则CallableStatment
              2 parameterize:主要针对PreparedStatment或则CallableStatment关联预编译
                              SQL语句中占位符进行修改
              
              3 update： 如何推送 insert ,update,delete
              4 query :  推送查询

     3.StatementHandler继承

             BaseStatementHandler:抽象类;
                                  负责实现 prpare方法

             RoutingStatementHandler：？？？？？



             BaseStatementHandler拥有三个子类

                SimpleStatmentHandler: Statement对象进行初始化
               PreparedStatementHandler: 预初编译对象PreparedStatement进行初始化
               CallableStatementHandler: CallableStatment
            

   4.关于三种数据库操作对象选择，不需要认为控制。

            执行sql语句有关

            情况1： select  *   from  order;   SimpleStatementHander  Statement
            情况2:  select  *   from order where orderId=? PreparedStatementHandler PreparedStatement
            情况3： call{pro}                   CallableStatementHandler   CallableStatment


     Dom4j.jar（XPath）  读取xml文档

```sql
                 create table dept{
                        deptno int primary key auto_increment,
                        dname  varchar(200),
                        loc    varchar(20)
                 }
```
         






              


