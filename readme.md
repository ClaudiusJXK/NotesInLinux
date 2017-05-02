### 系统命令
*  [Ctrl] + [Alt] + [F1] -[F6] :文字接口登入 tty1 ~ tty6 终端机
    [Ctrl] + [Alt] + [F7] :图形接口桌面

*  显示日期时间: date  　显示日历: cal  　计算器: bc 

* Tab :一次自动补全命令，两次显示以该字符开头的所有命令

* Ctrl-c :结束进程 　　Ctrl-d 键盘输入结束

* man/info + command　 用来显示命令的信息

## 简单常用命令
* ls -al 用来显示权限  档案连接数 档案拥有者 档案用户组 档案容量 以及档案名字等

	１．档案权限：drwxrwxrwx  -r-xr-x-wx   
２．d表示文件夹  　-表示文件   
３．ｒ表示读权限＝４ 　　w表示写权限＝２    　ｘ表示执行权限＝１   
４．三次rwx分别代表　档案拥有者权限　同组用户权限　其他组用户权限    

* chgrp chown chmod 用来改变文件或者文件夹的属性　　-R参数　对内部文件进行递归更改      

 	１．chgrp :改变档案所属群组   
 ２．chown :改变档案拥有者   
 ３． chmod :改变档案的权限　　chmod 777　filename　　7=4+2+1　读＋写＋执行权限    
 
 *  cd  
 
 	１．cd  　/file/…… 打开绝对路径　　其他格式，打开相对路径    
２．cd　..　打开上级菜单  

 * pwd  　mikdir　  rmdir   
 
	１．pwd:显示当前目录   
２．mkdir:建立一个新的目录　　   
　　　-m:设置权限　-p:递归创建文件夹（如mkdir  -p test1/test2/test3/test）　
３．rmdir:删除一个空的目录　　-p:同时删除上层的空目录（注意是空目录）   

* cp  　 mv　　rm   

	１．cp: 　cp [-adfilprsu] 来源文件(source) 目标文件(destination)    
　　　-r　递归持续复制，将文件夹以及子文件夹与子文件递归复制　-i　如果要覆盖则先询问   
２．mv:　mv  [-fiu] source destination   
　　　-f　强制（若目标存在则不询问）　-i　交互　　-u　若目标存在，则source比较新时才更新   
３．rm:　rm [-fir] 档案或目录  
　　　-f　强制删除，忽略存不存在　　-i　交互删除　　-r　递归删除   