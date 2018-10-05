# 10yue5ri
## 文件通配符
*匹配零个或多个字符  
？匹配任何单个字符  
~当前用户家目录  
[0-9]匹配数字范围  
[a-z]:字母  
[A-Z]:字母  
[wang]匹配列表中的任何的一个字符  
[^wang]匹配列表中的所有字符以外的字符   
[:digit:]任何数字，相当于0-9  
[:lower:]任意小写字母  
[:upper:]任意大写字母  
[:alpha:]任意大小写字母  
[:alnum:]任意数字或字母  
[:blank:]水平空白字符  
[:space:]水平或垂直空白字符  
[:punct:]标点符号  
[:print:]可打印字符  
[:cntrl:]控制（非打印）字符  
[:graph:]圆形字符  
[:xdigit:]十六进制字符  
## 创建空文件和刷新时间
touch命令
格式 ：touch [OPTION]...FILE...  
## 移动和重命名文件
mv  
## 删除
rm  
常用选项  
&ensp;&ensp;&ensp;&ensp;-i&ensp;&ensp;&ensp;&ensp;交互式  
&ensp;&ensp;&ensp;&ensp;-f&ensp;&ensp;&ensp;&ensp;强制删除  
&ensp;&ensp;&ensp;&ensp;-r&ensp;&ensp;递归  
&ensp;&ensp;&ensp;&ensp;--no-preserve-root&ensp;&ensp;删除/  
示例：  
&ensp;&ensp;&ensp;&ensp;rm -rf  /*
## 目录操作  
tree&ensp;&ensp;显示目录树  
&ensp;&ensp;&ensp;&ensp;-d:&ensp;&ensp;只显示目录  
&ensp;&ensp;&ensp;&ensp;-L&ensp;&ensp;lecel&ensp;&ensp;:指定显示的层级数目  
&ensp;&ensp;&ensp;&ensp;-P&ensp;&ensp;pattern&ensp;&ensp;:&ensp;&ensp;只显示由指定pattern匹配到的路径  
mkdir创建目录  
&ensp;&ensp;-p&ensp;&ensp;存在于不报错，且可自动创建所需的各目录  
&ensp;&ensp;-v&ensp;&ensp;显示详细信息  
&ensp;&ensp;-m&ensp;&ensp;MODE&ensp;&ensp;创建目录时直接指定权限  
&ensp;&ensp;rmdir&ensp;&ensp;删除空目录   
&ensp;&ensp;-p&ensp;&ensp;递归删除父空目录  
&ensp;&ensp;-v&ensp;&ensp;显示详细信息  
&ensp;&ensp;rm&ensp;-r&ensp;递归删除目录树
  
硬连接：对一个文件，起多个名字。  
软连接：原始文件一般路径用相对路径，相对路径一定相对于软链家而文件的路径。  

## 标准I/O和管道  
## 管道
管道（使用符号“|”表示）用来连接命令    
&ensp;&ensp;命令1的STDOUT发送给命令2的STDIN，命令2的STDOUT发送到命令3的STDIN  
&ensp;&ensp;STDERR默认不能通过管道转发，可利用2>&1或&实现  
&ensp;&ensp;最后一个命令会在当前shell进程的子shell进程中执行用来  
&ensp;&ensp;组合多种工具的功能  
&ensp;&ensp;Is&ensp;|&ensp;tr&ensp;&ensp;&ensp;'a-z'&ensp;&ensp;&ensp;&ensp;'A-Z'  

## 用户user  
&ensp;&ensp;令牌token,identity  
&ensp;&ensp;Linux用户：Username/UID  
&ensp;&ensp;管理员：root ,0  
&ensp;&ensp;普通用户：1-60000自动分配  
&ensp;&ensp;系统用户：1-499，1-999（CentOS7)  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;对登陆进程获取资源进行权限分配  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;登陆用户：500+，1000+ （CentOS7)   
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;交互式登陆  
## 组group  
&ensp;&ensp;Linux组：Groupname/GID  
&ensp;&ensp;管理组：1-499，1-999  （CenTOS7）  
&ensp;&ensp;普通组：500+ ，1000+（CENTOS7）  

## 组的类别
&ensp;&ensp;Linux组的类别  
&ensp;&ensp;&ensp;用户的主要组  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;用户必须属于一个且只有以恶搞主组  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;组名同用户名，且仅包含一个用户，私有组   
&ensp;&ensp;&ensp;&ensp;用户的附加组  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;一个用户可以属于零个或多个辅助组  

## 用户和组的主要配置文件  
&ensp;&ensp;/etc/passwd:用户及其属性信息（名称，UID，主组ID等）  
&ensp;&ensp;/etc/group:组机器属性信息  
&ensp;&ensp;/etc/shadow:用户密码及其相关属性  
&ensp;&ensp;/etc/gshadow:组密码及其相关属性  

## shadow文件格式
&ensp;&ensp;登陆用名  
&ensp;&ensp;用密码：一般用sha512加密  
&ensp;&ensp;从1970年1月1日起到密码最近一次被更改的时间  
&ensp;&ensp;密码再过几天可以被更改（0表示随时可被变更）  
&ensp;&ensp;密码再过几天必须被变更（99999表示永不过期）  
&ensp;&ensp;密码过期前几天系统提醒用户（默认一周）  
&ensp;&ensp;密码过期几天账号会被锁定  
&ensp;&ensp;从1970年1月1日算起，多少天后账号失效  

## 文件操作
&ensp;&ensp;vipw和vigr  
&ensp;&ensp;pwck和grpck  

## 用户和组管理命令
- 用户管理命令  
&ensp;&ensp;useradd&ensp;&ensp;&ensp;&ensp;增加用户  
&ensp;&ensp;usermod&ensp;&ensp;&ensp;&ensp;修改用户  
&ensp;&ensp;userdel&ensp;&ensp;&ensp;&ensp;删除用户  
- 组账号维护命令  
&ensp;&ensp;groupadd     
&ensp;&ensp;groupmod      
&ensp;&ensp;groupdel        


## 切换用户或以其他用户身份执行命令  
- su&ensp;&ensp;[options...]&ensp;&ensp;[-]&ensp;&ensp;[user&ensp;&ensp;[args..]]    
- 切换用户的方式：  
&ensp;&ensp;su UserName:非登录式切换，即不会读取目标用户的配置文件，不改变当前工作目录  
&ensp;&ensp;su - UserName：登陆式切换，会读取目标用户的配置文件切换至家目录，完全切换    
- root&ensp;&ensp;su至其他用户无需密码；非root 用户切换时需要密码  
- 换个身份执行命令：  
&ensp;&ensp;&ensp;&ensp;su&ensp;[-]&ensp;UserName&ensp;-c&ensp;'COMMAND'  
- 选项:&ensp;-l&ensp;&ensp;--login  
&ensp;&ensp;&ensp;su&ensp;-|&ensp;UserName&ensp;相当于su&ensp;-&ensp;UserName  

## 修改用户密码策略
- chage [OPTION]...LOGIN  
&ensp;&ensp;-d&ensp;&ensp;&ensp;LAST&ensp;DAY  
&ensp;&ensp;-E&ensp;&ensp;&ensp;expiredate&ensp;&ensp;&ensp;EXPIRE_DATE  
&ensp;&ensp;-I&ensp;&ensp;--inactive&ensp;INACTIVE  
&ensp;&ensp;-m&ensp;--mindays&ensp;MIN_DAYS  
&ensp;&ensp;-M&ensp;--maxdays&ensp;MAX_DAYS  
&ensp;&ensp;-l&ensp;&ensp;显示密码策略  
- 示例：  
&ensp;&ensp;chage&ensp;-d&ensp;0&ensp;tom&ensp;下一次登陆强制重设密码  
&ensp;&ensp;chage&ensp;-m&ensp;0&ensp;-M&ensp;42&ensp;-W&ensp;14&ensp;-I&ensp;7&ensp;tom  
&ensp;&ensp;chage&ensp;-M&ensp;2016&ensp;-09-10&ensp;tom  

## 更改组密码  
- 组密码：gpasswd  
- gpasswd&ensp;[OPTION]&ensp;GROUP  
&ensp;&ensp;&ensp;&ensp;-a&ensp;user&ensp;将user添加至指定组中  
&ensp;&ensp;&ensp;&ensp;-d&ensp;user&ensp;将指定组中移除用户user  
&ensp;&ensp;&ensp;&ensp;-A&ensp;user1，user2,...&ensp;设置由管理权限的用户列表    
- newgrp命令：临时切换主组  
&ensp;&ensp;如果用户本不属于此组，则需要组密码    

## 更改和查看组成员  
 - groupmems&ensp;[options]&ensp;[action]  
options:  
&ensp;&ensp;-g,&ensp;--group&ensp;groupname&ensp;&ensp;更改为指定组（只有root)  
Actions:  
&ensp;&ensp;-a,&ensp;&ensp;--add&ensp;username&ensp;&ensp;&ensp;指定用户加入组  
&ensp;&ensp;-d,&ensp;&ensp;--delete&ensp;username&ensp;从组中删除用户  
&ensp;&ensp;-p&ensp;--purge&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;从组中清除所有成员  
&ensp;&ensp;-l，&ensp;--list&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;显示组成员列表  
- groups&ensp;[OPTION].[USERNAME]...查看用户所属列表
