# SQL
SQL笔记
增：
1.1【插入单行】
insert [into] <表明> （列名）values(列值)
例：insert into Students(姓名，性别，出生日期) values ('张三','男'，'1990')

1.2【将现有数据添加到一个已有表】
insert into <已有的新表>（列名） select <原表列名> from <原表名>
例：insert into tongxueli('姓名','地址','电子邮件') 
select name,address,email
from Strdents

一：
alter table：修改数据库表结构
如需在表中添加列，请使用下列语法:
ALTER TABLE table_name
ADD column_name datatype
例：alter table Student
   add  fatherName  varchar

要删除表中的列，请使用下列语法：
ALTER TABLE table_name 
DROP COLUMN column_name
例：alter table Student
   drop column fahterName
   
二：
‘/’:执行命令
【1】：
append  text:追加文本命令
就是对上一个查询的结果再进行命令操作
例：append  where name='张三'

【2】
增加文本命令
input :后面跟一行
例：input order by name
input text:后面跟多行
例：
input 
order by
name

【3】
替换文本命令
change /旧文本/新文本：新文本替换前面的旧文本，
change /文本：删除这个文本
例：
select * from dept where rownum < 3;:查询此表的前两个数据
change /dept/student;:本来是查询的dept表，现在要换成查询student表的数据

change /rownum < 3;就是删除此限制，然后输出没有此限制的结果

【4】
删除命令
del :当一个命令语句执行完成后，再执行'/',还可以执行，但是 >del 后再查询就会出错，
del n :n表示删除第几行的命令
例如：
SQL>select *
 2  from 
 3  dept
 4  order by code
执行完成后再执行>del 4
则输出的就不是按code排序的数据

del 2 *
表示删除第二行以下的所有命令，包括第二行

【5】
清除缓冲区命令
> clear buffer;
> / :再执行之前的命令显示“缓冲区无可执行的程序”
【6】
查看缓冲区命令
> list: 查看缓冲区命令
> list n:查看缓冲区的第几行命令
> list n last :查看缓冲区n到最后一行的命令
【7】
保存命令
> ed  :edit的缩写
save 命令也可保存
例：save D：\sqltest.txt  :自动创建并保存到此目录下
【8】
查询结果格式化
> set pagesize n ：设置每页显示行数
> set newpage n :设置每页之间的行数（宽度）
show pagesize
show newpage
【9】
使自动换行的命令正常显示
> set linesize n
show linesize
【10】
列名格式化
> column 列名 format 格式化后的格式   ：格式化列
> colum  列名  clear ：取消列的格式化
【11】
保存查询结果
spool c:\ss.txt  :自动创建并保存到此文件
spool off  : 查询完成情况缓存

> spool c:\ss.txt
> select * from student
> spool off

【12】
调用外部脚本文件
例：>@c:sql.txt
【13】
注释（remark）和命令不能一行
> rem 这是一个注释


【14】
唯一性约束与主键约束的区别：
？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？？







   







