### 系统命令
*  [Ctrl] + [Alt] + [F1] -[F6] :文字接口登入 tty1 ~ tty6 终端机
    [Ctrl] + [Alt] + [F7] :图形接口桌面

*  显示日期时间: date  　显示日历: cal  　计算器: bc 

* Tab :一次自动补全命令，两次显示以该字符开头的所有命令

* Ctrl-c :结束进程 　　Ctrl-d 键盘输入结束

* man/info + command　 用来显示命令的信息

### 简单常用命令
* #### ls -al 用来显示权限  档案连接数 档案拥有者 档案用户组 档案容量 以及档案名字等    
	1. 档案权限：drwxrwxrwx  -r-xr-x-wx   
	2. d表示文件夹  　-表示文件   
	3. ｒ表示读权限＝４ 　　w表示写权限＝２    　ｘ表示执行权限＝１   
	4. 三次rwx分别代表　档案拥有者权限　同组用户权限　其他组用户权限    

* #### chgrp chown chmod 用来改变文件或者文件夹的属性　　-R参数　对内部文件进行递归更改      

 	1. chgrp :改变档案所属群组   
 	2. chown :改变档案拥有者   
	3. chmod :改变档案的权限　　chmod 777　filename　　7=4+2+1　读＋写＋执行权限    
 
 *  #### cd  
 
 	1.  cd  　/file/…… 打开绝对路径　　其他格式，打开相对路径    
	2. cd　..　打开上级菜单  

 * #### pwd  　mikdir　  rmdir   
 
	1. pwd:显示当前目录   
	2. mkdir:建立一个新的目录　　   
　　　-m:设置权限　-p:递归创建文件夹（如mkdir  -p test1/test2/test3/test）　
	3. rmdir:删除一个空的目录　　-p:同时删除上层的空目录（注意是空目录）   

* #### cp  　 mv　　rm   

	1. cp: 　cp [-adfilprsu] 来源文件(source) 目标文件(destination)    
　　　-r　递归持续复制，将文件夹以及子文件夹与子文件递归复制　-i　如果要覆盖则先询问   
	2. mv:　mv  [-fiu] source destination   
　　　-f　强制（若目标存在则不询问）　-i　交互　　-u　若目标存在，则source比较新时才更新   
	3. rm:　rm [-fir] 档案或目录  
　　　-f　强制删除，忽略存不存在　　-i　交互删除　　-r　递归删除   

*   #### cat 　tac　nl  more less head tail  
	1.  cat 由第一行开始显示档案内容  
	2. tac 从最后一行开始显示,可以看出 tac 是 cat 倒着写!  
	3. nl 显示的时候,顺道输出行号!  
	4. more 一页一页的显示档案内容  
	5.  less 与 more 类似,但是比 more 更好的是,他可以往前翻页!  
	6. head 叧看头几行   
	7. tail 叧看尾部几行   
	8. od 以二进制的方式读取档案内容   
* #### od 显示非文本文件  
	1. od[-t type] 以type格式输出   
	2.  type有 a/c/d/f/o/x 分别对应 默认，ASCII ，10进制，浮点型，8进制，16进制   
	
* #### 	umask  chattr  lsattr  
	1. umask：档案权限预设值，一共四位数，只看后三位。每位对应的数字为缺失的权限值   
	2. chattr [+-=][ASacdistu] 档案目录或名称  配置档案的其他属性    
	3. lsattr [-adR]  显示档案的其他属性   

* ####  SUID SGID SBIT 配置额外权限
	1. SUID  要求：二进制文件，当前用户具有x权限，该权限只在运行时有效，具有的权限为该程序owner的权限    
	2. SGId 与SUID功能相同，但是具有的也是目标所属群组的权限。切SGID可用于目录   
	3. SBIT   只对目录有效，作用为，若用户对该目录具有 w x 权限，则只有该用户与root可以删除其写入的文档。    
	4. 三者对应 4  2  1
* #### file  which  whereis  locate
	1. file： 显示文件类型   
 	2. which [-a] command ：找到指令的路径，-a表示all，返回所有的而不是第一个   
	3.whereis [-bmsu] 档案或目录名 ：    
	     -b 只找binary文件   -m 只找在说明文件manual路径下档案 -s source文件 -u 除上面三种以外的文件   
 	4. locate [-ir] keyword   
 		-i 忽略大小写差异  -r  正则表达式

	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	