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
	3. whereis [-bmsu] 档案或目录名 ：    
	     -b 只找binary文件   -m 只找在说明文件manual路径下档案 -s source文件 -u 除上面三种以外的文件   
	4. locate [-ir] keyword   
 		-i 忽略大小写差异  -r  正则表达式    
        
###打包压缩指令

*  #### 常见压缩方式   

		*.Z compress 程序压缩的档案;      
		*.gz gzip 程序压缩的档案;       
		*.bz2 bzip2 程序压缩的档案;     
		*.tar  tar程序打包的数据,并没有压缩过;   
		*.tar.gz tar程序打包的档案,其中并且经过 gzip 的压缩   
		*.tar.bz2  tar程序打包癿档案,其中并且经过 bzip2 的压缩   

*  #### gzip [-cdtv#]  文档名 
	1. -c :将压缩的数据输出到屏幕上,可透过数据流重导向来处理;    
	2. -d :解压缩的参数;    
	3. -t :可以用来检验一个压缩文件的一致性~看看档案有无错误;    
	4. -v :可以显示出原档案/压缩文件案的压缩比等信息;    
	5. -# :压缩等级,-1 最快,但是压缩比最差、-9 最慢,但是压缩比最好!预设是-6    



* #### tar  打包文件
	1. tar[] [-f] 文档名
	2.  压 缩:tar -jcv -f filename.tar.bz2 要被压缩的档案或目录名称    
	3. 查 询:tar -jtv -f filename.tar.bz2   
	4. 解压缩:tar -jxv -f filename.tar.bz2 -C 欲解压缩的目录   
	5. -c :建立打包档案,可搭配 -v 查察看过程中被打包的档名(filename)   
	6. -t :察看打包档案的内容含有哪些档名,重点在察看『档名』就是了;  
	7. -x :解打包或解压缩的功能,可以搭配 -C (大写) 在特定目录解开，特别留意的是, -c, -t, 	-x 可同时出现在一串指令列中。  
	8. -j :透过 bzip2 的支持进行压缩/解压缩:此时档名最好为 *.tar.bz2  
	9. -z :透过 gzip 的支持进行压缩/解压缩:此时档名最好为 *.tar.gz   
	10. -v :在压缩/解压缩的过程中,将正在处理的文件名显示出来  
	11. -f filename:-f 后面要立刻接要被处理的档名!建议 -f 单独写一个选项    
	12. -C 目录这个选项用在解压缩,若要在特定目录解压缩,可以使用这个选项     
	13. -p :保留备份数据的原本权限与属性,常用于备份(-c)重要的配置文件   
	14. -P :保留绝对路径,亦即允许备份数据中含有根目录存在之意;   
	15. --exclude=FILE:在压缩的过程中,不要将 FILE 打包   


* #### dump dump [-Suvj] [-level] [-f 备份档] 待备份资料  restore 还原
	1. -S :仅列出后面的待备份数据需要多少磁盘空间才能够备份完毕;
	2. -u :将这次 dump 的时间记录到 /etc/dumpdates 档案中;
	3. -v :将 dump 的档案过程显示出杢;
	4. -j:加入 bzip2 的支持!将数据迚行压缩,默认 bzip2 压缩等级为 2
	5. -level:就是我们谈到的等级,从 -0 ~ -9 共十个等级;
	6. -f:有点类似 tar 啦!后面接产生的档案,亦可接例如 /dev/st0 装置文件名等
	7. -W:列出在 /etc/fstab 里面的具有 dump 讴定癿 partition 是否有备份过?
	
### vim
* ####  一般模式    
	可以 删除　复制　粘贴，但是无法编辑内容  
    
* ####  编辑模式
	1. 『i, I, o, O, a, A, r, R』任意一个字符后进入编辑模式   
	2. 　esc 退出编辑模式


* #### 指令模式
	1.  : / ? 摁下这些后进入指令模式


### bash
* #### bash命令
* #### **输出** 
	echo+$变量名 取变量值
* #### **赋值**
	 variable=value 等号左右不能有空格，value与variable不能有空格，value若需要空格，使用“” ‘’ 将其包括起来
* #### **变量扩增**
	可用 "$变量名称" 或 ${变量} 累加内容 PATH="$PATH"/home/bin 原先值需要双引号，单引号不可
	4. **export**
	若该变量需要在其他子程序执行,则需要以 export 来使变量变成环境发量:『export PATH』
	5. **unset** 
	取消变量的方法为使用 unset :『unset 变量名称』
	6. **‘’ ”“**
	单引号与双引号的区别
	单引号与双引号的最大不同在于双引号仍然可以保有变量的内容,但单引号内仅能是一般字符 ,而不会有特殊符号。
	myname="$name its me" 结果为 VBird its me
	myname='$name its me' 结果为 $name its me
	7. **`**
	反单引号（\`）在一串指令中，在\`之内的执行将会先被执行，而其执行出来的结果讲作为外部的输入信息，类似与数字表达式的括号的作用
	8. **$**
	$是一个变量，代表当前的shell的线程代号
	9. **?**
	?是一个特殊变量，代表上一个指令所传回的值（0为执行成功，非0为执行错误）
	10. **read** 
		read [-pt] variable
		-p :后面可以接提示字符!
		-t :后面可以接等待的『秒数!』这个比较有趣~不会一直等待使用者啦!
	11. **declare / typeset**
	**变量类型**默认为**字符串**
	declare或typeset 是一样的功能,就是在声明变量类型。如果使用 declare 后面并没有接任何参数,那么 bash 就会主动的将所有的发量名称不内容通通叫出来,就好像使用 set 一样.
	declare [-aixr] variable:
    -a :将后面名为 variable 的发量定义成为数组 (array) 类型
	-i :将后面名为 variable 的发量定义成为整数数字 (integer) 类型
	-x :用法与 export 一样,就是将后面的 variable 发成环境发量;
	-r :将发量设定成为 readonly 类型,该发量不可被更改内容,也不能 unset
	12. **数组类型**
	可以直接赋值 array=(var1 var2 var3 ... varN)  **中间空格隔开，不用逗号**
	echo ${array[index]} 从0开始，要用大括号包着
    13. **变量的删除替代**
    ${变量#关键字} 若变量内容**从头开始**的数据符合关键字，则将符合的最短数据删除
    ${变量##关键字} 若变量内容**从头开始**得数据符合关键字，则将符合的最长数据删除
    ${变量%关键字} 若变量内容**从尾向前**的数据符合关键字，则将符合的最长数据删除
	${变量%%关键字} 若变量内容**从尾向前**的数据符合关键字，则将符合的最长数据删除
    ${变量/旧字符串/新字符串} 若变量内容符合旧字符串，则**第一个**旧字符串会被新字符串取代
    ${变量/旧字符串/新字符串} 若变量内容符合旧字符串，则**第一个**旧字符串会被新字符串取代
	14. **测试并赋值**
	var=${var-content} 如果var有值则不变，无值则复制为content
    15. **alias, unalias**
    为命令设置别名或者取消别名
    alias lm='ls -al | more'
	unalias lm
    16. **一些组合按键命令**
    Ctrl + C 终止目前的命令
	Ctrl + D 输入结束 (EOF),例如邮件结束的时候;
	Ctrl + M 就是 Enter 啦!
	Ctrl + S 暂停屏幕的输出
	Ctrl + Q 恢复屏幕的输出
	Ctrl + U 在提示字符下,将整列命令初除
	Ctrl + Z 『暂停』目前的命令
	17. **通配符与特殊符号**
	**\*** 代表『0个到无穷多个』任意字符
	**?**  代表『一定有一个』任意字符
	**[ ]**同样代表『一定有一个在括号内』的字符(非任意字符)。例如 [abcd] 代表『一定有一个字
	符, 可能是 a, b, c, d 这四个任何一个』
	**[ - ]**若有减号在中括号内时,代表『在编码顺序内的所有字符』。例如 [0-9] 代表0到9之间的所有数字
	**[^ ]**若中括号内的第一个字符为指数符号 (^) ,那表示『反向选择』,例如 [^abc]代表一定有一个字符,只要是非 a,b,c的其他字符就接受的意思。
	18. **数据流重导向**












