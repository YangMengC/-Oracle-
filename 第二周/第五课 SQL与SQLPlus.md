# 第五课 SQL与SQLPlus

## 1. 初始SQL

### 什么是SQL

- **结构化查询语言(Structured Query Language)**，由ANSI标准制定的标准语言，

- 是一种数据库查询和程序设计语言，用于存取数据以及查询、更新和管理关系数据库系统。

- 补充
  
  - 什么是ANSI？
    
    - 美国国家标准学会（AMERICAN NATIONAL STANDARDS INSTITUTE: ANSI）

### SQL有哪些语句

- **数据查询语言（DQL:Data Query Language）**
  
  - 其语句，也称为“数据检索语句”，用以从表中获得数据，确定数据怎样在应用程序给出。
  - DQL常用的保留字有SELECT、WHERE、ORDER BY、GROUP BY、HAVING。

- **数据定义语言（DDL：Data Definition Language）**
  
  - 其语句包括动词CREATE和DROP，在数据库中创建新表或删除表（CREAT TABLE 或 DROP TABLE）。

- **数据操作语言（DML：Data Manipulation Language）**
  
  - 其语句包括动词INSERT，UPDATE和DELETE。它们分别用于添加，修改和删除表中的行。

- **数据控制语言（DCL：Data Control Language）**

- 通过GRANT或REVOKE获得许可，确定单个用户和用户组对数据库对象的访问。

### SQL的书写

- SQL语句不是大小写敏感的。建议关键字用大写，其他用小写。
- SQL语句可以分布在一行或者多行中。
- 关键字不能进行缩写，也不能分布在两行。
- 一般地，不同的子句写在不同的行为宜。
- 经常用跳格键或者缩进来增强可读性。

## 2. 连接SQL的工具

### 工具有哪些？

- 图形化工具
  - PL/SQL Developer
  - TOAD for Oracle
  - Oracle SQL Developer
- 命令行工具
  - sqlplus

### 最常用的工具

- sqlplus
  
  - 不受操作系统影响，只要安装了Oracle软件就可以使用。
  - 不需要任何配置就可以使用
  - 使用SQL来操作管理数据库
  - DBA最常用的工具

## 3. SQL与SQLPlus的关系

![image-20211125155453548](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155453548.png)

## 4. SQLPlus的使用

### 如何登录SQLPlus

- 窗口环境登录
  
    ![image-20211125155503406](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155503406.png)

- 命令行登录
  
  ```sql
  SQL>sqlplus [username [/passwode [@database]]]
  ```

### SQLPlus有哪些命令

![image-20211125155509387](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155509387.png)

### 查看当前连接的用户

```sql
SQL>show user;
```

- 解锁某个用户
  
  ```sql
  SQL>alter user scott account unlock;
  ```

- 修改某个用户密码
  
  ```sql
  SQL> alter user  scott account unlock; 
  ```

- 修改当前用户密码
  
  ```sql
  SQL> password
  ```

- 给某个用户设置密码并解锁
  
  ```sql
  SQL> alter user hr identified by hr account unlock;
  ```

### 查看表的结构

```sql
SQL>desc tablename;
```

### 查看执行SQLPlus缓存

- 查看不执行
  
  - L[ist] 列出所有缓存，不区分大小写
    n 数字1，2，... 列出第n行的缓存，并设定当前指向第n行
  - / 执行缓存语句

- 查看并执行
  
  - R[UN] 列出缓存并执行，中括号表示可选的，就是说中括号里的内容可以省略。
    R[un] 中括号中的字符串省略原则是按顺序，若u省略，则n必须省略。
    即 r ru run 都是有效的命令，但 rn 不是。

### 修改追加缓存内容

- 修改当前缓存
  
  - change
    
      C[HANGE] sepchar old [sepchar [new[sepchar]]]
    
      ![image-20211125155520590](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155520590.png)

- 追加当前缓存
  
  - append
    
    - A[PPEND] text
      
      ![image-20211125155528029](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155528029.png)

### 在SQLPlus执行脚本

- 将缓存保存到脚本
  
  - SQL>save filename.sql
  
  ![image-20211125155534430](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155534430.png)

- 删除缓存
  
  - SQL>del 1 *
    
    - 删除缓存中1-*行
    - *表示当前行

- SQL>del 1
  
  - 删除第一行
  
  - SQL>del *
    
    - 删除当前行
    
    ![image-20211125155540837](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155540837.png)

- 读取文件内容到缓存
  
  - SQL>get filename.sql
  
  ![image-20211125155547082](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155547082.png)

- 执行脚本
  
  - SQL>start filename.sql
  - SQL>@ filename.sql
  
  ![image-20211125155552298](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155552298.png)

- 将语句执行结果输出到文件
  
  - SQL> spool filename.out
  
  - SQL>spool off  (结束,会写入上面的文件结尾)
    
    ![image-20211125155602010](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155602010.png)
    
    - 文件内容

      ![image-20211125155618209](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155618209.png)

### 定制SQLPlus环境

- 使用 SET 命令来控制当前的会话
  
  - 查看可以SET的变量
    
    - SQL>HELP SET

- 常用变量
  
  - FEEDBACK {6 | n |OFF | ON} 是否显示查询结果
  - HEADING {OFF | ON} 列的头信息
  - LINESIZE {80 | n} 每一行的长度
  - LONG {80 | n} 设置显示long,lob等型字段的长度
  - PAGESIZE {24 | n} 页面的尺寸
  - PAUSE {OFF | ON | text} 设置滚屏是否自动
  - TIMI[NG] {OFF|ON} 是否显示执行语句的消耗的时间
  - TIME {OFF | ON} 是否在SQL>前显示当前时间
  - ECHO {OFF | ON} 是否先打印内容再执行

- 保存定制结果
  
  - $ORACLE_HOME/sqlplus/admin/glogin.sql文件包含在登录时需要执行的标准SET命令及其他命令.
    可以更改glogin.sql以包含其他SET命令.

### 格式化输出

- SQL*Plus 格式命令
  
  - - COLUMN [column option]
  - - TTITLE [text | OFF | ON]
  - - BTITLE [text | OFF | ON]
  - - BREAK [ON report_element]
  - - COLUMN命令 控制列的输出
  - - CLE[AR]: 清除掉所有的列格式

- COLUMN命令
  
  - FOR[MAT] format: 使用格式模型来改变列的显示。
    
    - ![image-20211125155645198](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\image-20211125155645198.png)
  
  - HEA[DING] text:设置列头
  
  - JUS[TIFY] {align}: 将列头对齐到左边、中间、或者右边
  
  - 创建列头
    
    - COLUMN ename HEADING 'Employee|Name'( | 表示在表头换行显示) FORMAT A15
    - COLUMN sal JUSTIFY LEFT FORMAT $99,990.00
    - COLUMN mgr FORMAT 999999999 NULL 'No manager'
  
  - 显示ENAME 列的显示格式
    
    - COLUMN ename
  
  - 清除 ENAME 列的设置.
    
    - COLUMN ename CLEAR

## 5. 结构图

![第五课 SQL与SQLPlus](D:\Documents\Oracle运维实战\第二周\第五课 SQL与SQLPlus.assets\第五课 SQL与SQLPlus.png)
