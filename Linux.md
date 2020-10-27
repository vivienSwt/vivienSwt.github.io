# Linux 基础命令
@[TOC](这里写目录标题)

---

## 一. 操作系统的常见分类

**1. 桌面操作系统**
 - Windows
- macOS
- Linux

**2. 服务器操作系统**
 - Linux(占比非常高)
 - Windows Server

**3. 移动端操作系统**
 - iOS(苹果)
 - Android(基于Linux系统)

**4. 嵌入式操作系统**
- Linux(自动贩卖机/收银台/汽车中控)
- Windows CE(不常见)
---
## 二. Linux 系统特点
- 开源(源代码可见)
注：开源不意味着一定是免费的(要看具体的开源协议)
- 安全稳定
- 移植性好
- 高性能
---
## 三. Linux 系统的分类
市面上常见的Linux系统都有一个共同的类别名称：Linux发行版;
Linux发行版：在内核版基础上，额外增加一些应用软件和图形化操作页面;
![Linux系统分类](https://img-blog.csdnimg.cn/20201002181115259.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_center)

---
## 四. Linux 系统的文件和目录
### 特征
- Linux系统只有一个根目录 /
- 没有盘符的概念
### 常用目录
- / : 根目录(所有文件和文件夹的存放位置)
- /home/用户名 : 普通用户的家目录
- /root : Linux系统超级管理员的家目录
- /bin  /usr/bin : 存放Linux系统命令
- /etc : 存放Linux的配置文件
---
## 五. Linux 命令快速演示
|序号  | 命令 | 对应英文 | 作用 |
|--|:--|:--|:--|
| 1 | ls | list | 查看当前文件夹内容 |
| 2 | cd | Chang Directory | 切换文件夹 |
| 3 | touch 文件名 |  | 创建空文件 / 修改时间 |
| 4 | mkdir | Make Directory | 创建目录 |
| 5 | rm 文件名 | Remove | 删除文件 |
| 6 | rm -r 目录名 |  | 删除目录 |

- Linux的命令和文件名目录名区分大小写
	- D和d是不同的名字
---
## 六. Linux 命令的基本格式
```shell
命令基本组成：
命令主体 -命令选项 命令参数

常见形式：
1) 命令主体
2) 命令主体 -命令选项
3) 命令主体 参数
4) 命令主体 -命令选项 参数

注意事项:
1) 命令主体必须存在, 命令选项和命令参数是可选的
2) 命令主体 : 命令名字;
   命令选项 : 起到对命令主体进行功能扩展或限制的作用;
   命令参数 : 文件名/文件路径
```
---
## 七. 查看Linux 系统命令帮助信息
1. **命令 --help**
```shell
例如 : ls --help
	  touch --help
帮助信息的作用 : 主要可以通过帮助信息, 查看某一命令主体拥有哪些选项
```
2. **man 命令**
```shell
例如 : man ls
       man touch
注意 : 实际应用推荐使用第一种方法
```
- 在man命令界面下快捷键:
	- 空格键 : 向下翻页
	- b : 向上翻页
	- q : 退出man的界面
---
## 八. Linux 命令通用知识点
### 1. 通配符
> 通配符 : 可叫 文件替换符号, 符号具备特殊含义;
> 例如: 文件名 test, 通配符可写成: * 或 ????

`*` : 代表可以匹配任意长度的文件名( **所有** )
`?` : 代表可以匹配单个字符, 文件名有多个字符则使用多个?进行匹配
`[]` : 表示一个范围

	例如 : 
	[aeg] : 匹配文件名是 a 或 e 或 g
	[a-c] : 匹配文件名是 a 或 b 或 c
	ls [a-c]* : 查看以 a 或 b 或 c 开头, 后面任意多个字符的文件或目录内容

![Linux{}](https://img-blog.csdnimg.cn/20201003003555303.png#pic_left)![Linux通配符](https://img-blog.csdnimg.cn/202010030057321.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)
![Linux通配符](https://img-blog.csdnimg.cn/20201003010230276.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)
### 2. 路径
#### 1) 绝对路径
-  **路径源头固定不变,常见表达形式**
	-  ' / ' : 从根目录开始
	-  ' ~ ' : 当前用户家目录(如: /home/admin)
#### 2) 相对路径
 - **从当前目录为起点, 常见表示形式**
 	- ' . ' : 当前路径下
 	- ' .. ' : 当前目录的上一层(父层级
---
## 九. Linux常用命令
---
### <font color='red'>1. pwd</font>
>查看当前所在路径

---
### <font color='red'>2. ls</font>
>查看当前路径下有哪些文件/目录
> -a : 显示目录下的所有文件(包含隐藏文件)
> -l : 显示文件详细信息 ( 列表形式 )
> -h : 显示文件大小, 按人性化方式显示

` -l 参数结果说明`
![-l 参数结果说明](https://img-blog.csdnimg.cn/20201003110417160.png#pic_center)
|  | 说明 |
|:--|:--|
| **文件类型** | **d** : 目录, **-** : 文件, **l** : 链接文件 |
| **文件权限** | **r** : 读, **w** : 写, **x** : 执行 |
| **硬链接数** | 文件被硬链接的次数 |
| **文件属主** | 文件所属用户 |
| **文件大小** | 文件大小, 默认单位为: 字节 |
| **文件修改时间** | 文件修改时间 |
| **文件或目录名** | **./** : 当前目录, **../** : 上一级目录, **.文件名** : 代表隐藏文件 |

![ls](https://img-blog.csdnimg.cn/20201003104842726.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)
![ls](https://img-blog.csdnimg.cn/20201003105234781.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)
![ls](https://img-blog.csdnimg.cn/20201003105448974.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---
### <font color='red'>chmod</font>
**文件读写权限解释**
>rwx rwx rwx
>分为三组
>第一组 : 文件所属用户 对文件的权限 ( **u : user 用户**)
>第二组 : 文件所属组 对文件的权限 ( **g : group 组** )
>第三组 : 其他用户对文件的权限 ( **o : other 其他** )
> r 读, w 写, x 执行
> rw- rw- r--  文件所属用户可读写、不可执行; 文件所属组可读写、不可执行; 其他用户只读;
---

**字母法**
 1. u : user 用户
 2. g : group 组
 3. o : other 其他
 4. a : all 所有
 5. `+` : 增加权限
 6. `-` : 删除权限
 7. `=` : 权限直接赋值
![chmod字母法](https://img-blog.csdnimg.cn/20201003134753591.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

**数字法**
- r : 4
- w : 2
- x : 1
- 举例
	- : r & w
	-  : r & w & x
	-  : 无任何权限
```shell
chmod 777 a.txt     rwx rwx rwx 
chmod 567 a.txt     r-x rw- rwx 
chmod 000 a.txt     --- --- --- 
chmod 777 -R 文件或目录    #递归修改文件权限
```

---
### <font color='red'>cd</font>
>切换当前目录
~~~ shell
cd      # 回到用户主目录
cd ~    # 回到用户主目录
cd 目录名     # 进入指定目录
cd /    # 回到根目录
cd ..   # 回到上级目录
~~~

---
### <font color='red'>touch</font>
> 如果文件不存在, 创建一个空文件
> 如果文件存在, 修改文件最后修改时间
```shell
touch a.txt     # 创建a.txt文件
touch a.txt     # 文件已存在, 则修改时间
touch test a b  # 创建 test文件 a文件 b文件
```

---
### <font color='red'>mkdir</font>
>创建空目录
>注意 : 如果有同名的目录或者文件名, 创建会失败报错
>-p  创建一个有层级关系的目录( 递归创建 )

```shell
mkdir abc     # 创建一个空目录abc
mkdir a b c   # 创建a目录, b目录, c目录
mkdir -p a/b/c  # 递归创建a/b/c目录
```

---
### <font color='red'>rm</font>
>删除文件或目录
>-r  删除目录
>-f  强制删除, 即使不存在, 也不报错
```shell
rm a.txt    # 删除文件
rm -r abc   # 删除目录
rm -f a.txt  # 强制删除文件, 即使文件不存在, 也不报错
rm -rf *     # 强制删除所有文件/目录( 删库跑路 )
```

---
### <font color='red'>cp</font>
>拷贝文件
>cp 源文件 目标文件
>-i : 目标文件如果存在, 提示是否覆盖
>-r : 拷贝目录必须加-r参数

```shell
touch a.txt
mkdir abc
cp a.txt ./abc/a.txt      # 把a.txt拷贝到abc目录, 名字还是为a.txt
cp a.txt ./abc/b.txt      # 把a.txt拷贝到abc目录, 名字为 b.txt
cp -i a.txt ./abc/a.txt   # abc目录已经存在a.txt, 给出是否覆盖的提示
cp -r abc aaa    # 把目录abc拷贝为aaa
```

---
### <font color='red'>mv</font>
> 移动文件/目录
> mv 源文件 目标文件
> - mv命令和cp命令的使用方式基本一致
> - cp后 源文件和目标文件都存在
> - mv后 源文件不存在

```shell
mv a.txt abc/a.txt    # 把文件 a.txt移动到abc目录下, 名字还叫 a.txt
cd abc
mv a.txt ../a.txt   # 把文件 a.txt移动到上级目录, 名字为 a.txt
cd ..
mv a.txt b.txt  # 把文件a.txt 改名为b.txt
```
- **练习**
![mv练习](https://img-blog.csdnimg.cn/20201003173418210.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)
![mv练习](https://img-blog.csdnimg.cn/20201003175321764.png#pic_left)
---

### <font color='red'>cat</font>
>查看文件内容
>cat 文件名
>-n : 显示行号
>-b : 只为非空行编号
```shell
cd /proc
cat cpuinfo     # 查看文件cpuinfo内容
cat -n cpuinfo  # 显示行号
cat -b cpuinfo  # 只为非空行编号
```
---

### <font color='red'>more</font>
>分屏查看文件内容
>`more 文件名`
>	- 空格 : 下一页
>  - b : 上一页
>  - q : 退出
```shell
more meminfo
```
---

### <font color='red'>head</font>
>查看文件开头部分内容, 默认显示前10行
>`head -行数 文件名` : 查看文件前n行
```shell
head a.txt    # 默认查看前10行
head -20 a.txt    # 查看前20行
```
---

### <font color='red'><b>tail</b></font>
>查看文件结尾部分内容, 默认显示后10行
>`tail -行数 文件名` : 查看文件后n行
>`tail -f 文件名` : 动态(实时)查看日志文件内容
```shell
tail a.txt    # 默认查看后10行
tail -20 a.txt    # 查看后20行
tail -f ping.log   # 动态查看日志文件内容
```
```
注意 : 
1. 日志文件 : 系统或软件运行过程中, 负责记录运行过程信息的文件( 可以通过内容判断bug出现原因 )
2. 系统相关日志的存放位置 : /var/log
3. 项目相关日志的存放位置 : 需要根据项目询问对应的开发人员
```
---

### <font color='red'>grep</font>
>在指定的文件中, 显示指定的内容
>grep  要显示的内筒 文件名
>-n : 显示行号
>-v : 显示不匹配的内容
>-i : 忽略大小写
```shell
grep "cpu" cpuinfo   # 显示有字符cpu的行
grep -v "cpu" cpuinfo  # 显示不包含cpu的行
grep -n "cpu" cpuinfo  # 显示包含cpu的行, 同时显示行号
grep -i  "cpu" cpuinfo  # 显示包含cpu的行, 并且忽略大小写
```
>Linux命令输入错误, 用ctrl + c 可以退出错误界面
---

### <font color='red'>模式查找(正则表达式)</font>
- `^字符`
	- 查找以指定字符开头的行
- `字符$`
	- 查找以指定字符结尾的行
- `^字符.*字符$`
	- 查找以指定字符开头,以指定字符结尾的行
```linux
grep "^a" cpuinfo    # 查找以a开头的行
grep "z$" cpuinfo    # 查找以z结尾的行
grep "^a.*z$" cpuinfo   # 查找以a开头且以z结尾的行
```
---

### <font color='red'>echo</font>
>回显
```shell
echo hello   --->  echo
```
---

### <font color='red'>clear</font>
>清屏
```shell
clear
ctrl + L
```
---

### <font color='red'>重定向</font>
>把一个命令执行的结果不显示在屏幕上, 而是放入一个指定的文件中
>`>` : 把命令执行结果放入指定文件, 如果文件存在, 覆盖文件; 如果不存在,则创建文件
```shell
ls -l > a.txt    # 把ls -l执行结果放入指定的文件中   --> a.txt 显示ls -l执行的结果
echo hello > a.txt   # 把echo hello 执行结果覆盖放入a.txt中  --> 将a.txt原有的内容覆盖为hello
```
---

### <font color='red'>追加重定向</font>
> `>>` : 追加重定向
>
>    - 如果指定文件不存在, 就创建文件; 如果指定文件存在, 则在已有的内容后面追加
```shell
echo hello world >> a.txt   # 如果a.txt已经存在, 就在已有的内容后面追加
结果:
hello
hello world
```
---

### <font color='red'>管道符</font>
>把一个命令执行的结果, 做为另一个命令的输入
>`|` : 竖杠
> `命令1 | 命令2`
```shell
ls -al > a.txt
more a.txt
# 上面的语法, 是实现把 ls -al 的结果能分屏显示
等价于:
ls -al | more
```
```shell
ls -al > a.txt
grep "^d" a.txt
# 显示 ls -al 结果中以d开头的行
等价于: 
ls -al | grep "^d" a.txt
```
> 管道中的命令1, 一定要有输出结果, 命令2一般都能处理文件

**练习**
> 用ls, 结合管道, 显示主目录下以**s结尾的目录**, 包括隐藏目录
> 答案:
> `ls -al | grep "^d.*s$"`
---

### <font color='red'>find</font>
>从指定目录开始查找所有子目录是否有指定的文件
> `find 起始目录 -name 文件名`   # 目标文件名里可以使用通配符(***/?/[]**)
```shell
find . -name "a.txt"   # 从当前目录开始查找所有子目录 a.txt
find / -name "*.txt"   # 从根目录开始查找所有子目录, 扩展名为.txt, 文件名任意
find . -name "?.txt"   # 从当前目录开始查找所有子目录, 扩展名为.txt, 文件名为任意一个字符
```

---

### <font color='red'>which</font>
>查找文件, which指令会在环境变量$PATH设置的目录里查找符合条件的文件;
>`which 程序名` : 可查看程序的安装位置 ( 绝对路径 )

```shell
which mysqld
```
![which](https://img-blog.csdnimg.cn/20201006112948824.png#pic_left)

---

### <font color='red'>ln</font>
**软链接**
> 类似windows下的快捷方式
> `ln -s 源文件 目标软链接文件`
```shell
ln -s a.txt a1   # 给文件a.txt 创建一个软链接a1
```

**硬链接**
> `ln 源文件 目标硬链接文件`
```shell
ln a.txt a2
ln a.txt a3
```
- 硬链接和软链接的区别
	- 硬链接文件总是和源文件一样大小
	- 软链接很小, 大小和源文件无关
	- 硬链接**会影响**ls -l 查看文件时, 文件的硬链接数
	- 软链接**不会影响**ls -l 查看文件时, 文件的硬链接数
	- 当源文件被删除, 软链接文件同时失效
	- 当源文件被删除, 硬链接可以继续使用
- 不管软链接还是硬链接, **文件内容总是和源文件同步**
---

### <font color='red'>gzip</font>
>压缩和解压文件
>gzip只能对一个文件进行压缩
>gzip只能压缩文件, 不能压缩目录
><br />
`gzip 文件名`     # 压缩, 压缩后`文件不存在`
`gzip -d 文件名.gz`    # 解压, 解压后gz`压缩包不存在`


```shell
ls -al > a.txt   # 快速的生成一个文件
gzip a.txt   # 把a.txt压缩为a.txt.gz, 压缩之后a.txt就不存在了
gzip -d a.txt.gz  # 压缩a.txt.gz, 解压之后a.txt.gz就不存在了
```
---

### <font color='red'>ungzip</font>
>类似windows上的压缩软件, 压缩后的格式为zip格式



---

### <font color='red'>df</font>
> 查看磁盘使用情况
```shell
df
df -h   # 用人性化方式显示大小
```
![df](https://img-blog.csdnimg.cn/20201004161907454.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---

### <font color='red'>ps</font>
> 查看系统进程 (正在运行的程序)

```shell
ps -aux / ps aux   # 查看当前系统中所有进程信息
ps -aux | grep 程序名   # 能获取目标进程的PID
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201004163242524.png#pic_left)

- USER : 代表启动进程的用户名
- PID : 每个进程都有一个唯一的编号
- COMMAND : 进程的名字

---

### <font color='red'>kill</font>
> 杀死进程
> `kill PID`
> `kill -9 PID` : 彻底杀死进程(遇到杀不掉的进程, 加-9参数)

![kill](https://img-blog.csdnimg.cn/20201004164106751.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---

### <font color='red'>top</font>
> `top` : 动态查看进程信息
> 退出top : 在top界面下按 `q`

```shell
top
```
![top](https://img-blog.csdnimg.cn/20201004165305272.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---

### <font color='red'>netstat</font>
> 1.`netstat -anptu` : 获取当前系统的网络相关信息( 获取开放的端口号 )
> 2.以root用户权限执行`netstat -anptu` 命令时, 可查看端口号和程序名
> 3.`netstat -anptu | grep 端口号/程序名` : 查看端口号或程序名(  **需要使用root用户权限** )

```shell
su -  # root用户
netstat -anptu | grep 3306   # 查看端口号为3306的网络信息( PID/程序名 )
exit  # 退出root用户, 进入普通用户
netstat -anptu  # 普通用户无法查看PID和程序名
```
![netstat](https://img-blog.csdnimg.cn/2020100523255078.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_leftr)

---

### <font color='red'>lsof</font>
>`lsof -i:端口号`  : 查看占用端口号 的PID和程序名( **需要使用root用户权限** )
```shell
su -  # root用户权限
lsof -i:3306  # 查看3306端口号占用情况( PID和占用3306端口的程序名 )
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005235001886.png#pic_left)

---

### <font color='red'>ping</font>
>检查与目标主机是否可网络连通
>`ping 目标主机的ip或域名`
>`ping baidu.com `	: 会一直ping, ctrl+c暂停
>`ping -c 5 192.168.1.66`  : ping 5次后暂停

```shell
ping baidu.com    # ctrl + c暂停
ping -c 5 220.181.38.148   # ping 5次后暂停
```

---

### <font color='red'>ifconfig</font>
>`ifconfig` : 查看网卡信息
>`ip addr` : CentOS 7 中默认查看网卡信息的命令

![ifconfig_ubuntu](https://img-blog.csdnimg.cn/20201006104904570.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

![ip addr_CentOS](https://img-blog.csdnimg.cn/20201006104804402.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---

### <font color='red'>su</font>
- **切换用户**
>`su - 用户名`  :  切换用户, 同时当前目录修改为目标用户的主目录
>`su -`  : 切换root用户, 当前目录修改为root用户主目录(/root)
>`su 用户名`  : 切换用户, 但不改变当前目录
>`su ` : 切换root用户, 不改变当前目录

![su](https://img-blog.csdnimg.cn/20201006204058810.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

- **退出切换的用户**
>`exit`

---

### <font color='red'>useradd</font>
- 添加用户必须是root才能有权限
- useradd
	- -d : 指定用户的主目录
	- -m : 如果主目录不存在, 自动创建
>linux增加用户有个习惯, 所有用户的主目录都在 /home目录下, 用户的主目录名和用户名相同

```shell
# 添加一个用户, 名字叫user1, 主目录在/home/user1目录, 设置密码为123456
su -    # 切换到root用户
useradd -d /home/user1 user1 -m   # 创建一个用户user1
passwd user1   # 为user1设置密码为123456
# 密码需要输入两次
```

---

### <font color='red'>passwd</font>
- 修改用户密码
- root 用户可以修改任何用户的密码
- 普通用户只能修改自己的密码
```shell
passwd 用户名   # 修改制定用户的密码, 需在root用户下
passwd  # 修改用户自己的密码
```
![passwd](https://img-blog.csdnimg.cn/20201006230119366.png#pic_left)

---

### <font color='red'>userdel</font>
- 删除用户
-  -r : 删除用户的同时删除用户的主目录和邮箱
-  -f : 强制删除, 即使用户登录了, 也删除

```shell
su -  # root用户权限
userdel -rf user  # 强制删除用户user1, 同时删除用户目录和邮箱
```

---

### <font color='red'>whoami</font>
>显示的是当前用户下的用户名
> 当系统用户特别多, 用su切换多次, 容易忘记当前是哪个用户登录
```shell
whoami
```
![whoami](https://img-blog.csdnimg.cn/20201006232629729.png#pic_left)

---

### <font color='red'>who</font>
>`who -u` : 显示当前真正登录系统中的用户（不会显示那些用su命令切换用户的登录者）

```shell
who -u
```
![whoami & who](https://img-blog.csdnimg.cn/20201006232434971.png#pic_left)

---

### <font color='red'>vi</font>
#### vi的三种模式
- **命令模式**
	- 刚进入vi界面的时候, 是命令模式
	- 在命令模式下按`i`进入输入模式
	- 在命令模式下按 冒号 `:` 进入末行模式
- **输入模式**
	- 进入输入模式以后可输入内容
	- 在输入模式下按`ESC`回到命令模式
- **末行模式**
	- 在末行模式下输入`wq`, 保存文件退出vi
<br>
- 输入模式不能直接进入末行模式
- 不管在哪个模式下, 只要按`ESC`键, 都会回到命令模式
![vi三种模式](https://img-blog.csdnimg.cn/20201006234116686.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01vamllXzY2,size_16,color_FFFFFF,t_70#pic_left)

---

#### vi三种不同启动方式
- **vi 新文件名**
	- 创建一个空文件
- **vi 已有文件名**
	- 打开一个已有的文件
- **vi**
	- 直接启动vi, 不打开任何文件

---

#### 命令模式下的指令
##### 插入指令
- `i` : 在光标所在当前位置插入
- `a` : 在光标所在位置后插入
- `o` : 在光标所在行的下一行插入
- `I `: 在光标所在行首插入
- `A` : 在光标所在行尾插入
- `O` : 在光标所在行的上一行插入

##### 进入末行模式命令
- 冒号 `:`

##### 删除指令
- `x` : 删除光标前一个字符
- `dd` : 删除光标所在的行
- `ndd` 
	- `n` 是一个数字, 代表删除光标所在下面的**n行**
	- 3dd, 删除3行

##### 撤销指令
- `u ` : 撤销
- `ctrl + r` : 反撤销

##### 复制粘贴指令
- `yy` : 复制光标所在的行
- `nyy` : 
	- 复制光标所在下方**n行**
	- 5yy, 复制5行
- `p` : 粘贴

##### 行定位指令
>行定位指令 快速定位到指定行
>如果文件内容特别多, 通过上下光标定位行,比较繁琐
- `G` : 到最后一行
- `1G` : 到第一行
- `nG` : 
	- n 是数字
	- 到**第n行**

##### 查找指令
- `/要查找的字符串`
- n查找下一个
- N查找上一个

```
/root  # 在文件中查找有无字符串root
```

---

#### 末行模式的指令
- `w` : 保存, 不退出vi
- `w 文件名`
	- 把内容保存为指定的文件
	- 如果启动vi时没有指定文件, 若想保存内容, 必须用`w 文件名` 指定要保存的文件
- `q`
	- 退出vi
	- 如果文件内容已经改变, 就不能使用q 退出vi
- `wq` : 保存文件, 并退出vi
- `q!` : 不保存文件, 退出vi

---

**练习**
```
把根目录下proc目录下cpuinfo文件拷贝到用户的当前目录
用vi把文件的第五行修改为aaaaaaaaa
保存退出
```
**答案**
```
cd   # 回到主目录
cp /proc/cpuinfo .   # 把/proc/cpuinfo拷贝到当前目录
chmod u+w cpuinfo   # 给cpuinfo文件的用户添加w写权限
vi cpuinfo
把光标移动到第五行, 进入输入模式
在输入模式下删除第五行已有的内容
在输入模式下输入aaaaaaa
按ESC
输入 :wq
more cpuinfo  # 查看修改是否成功
```

---

#### 非正常退出vi的处理方法
> 当打开vi后, 并且修改文件内容, 没有保存退出, 而是非正常关闭了vi, 下次启动vi会出现异常退出的提示
- `O` : 只读方式打开
- `E` : 编辑之前vi没有修改过的内容
- `R` : 编辑vi修改后的内容
- `D` : 直接删除交换文件
- `Q` : 直接退出vi, 不做任何操作

---

### <font color='red'>reboot</font>
>重启系统

---

### <font color='red'>shutdown</font>
>`shutdown -h now` : 关闭系统( 定时关机 )

---

### <font color='red'>查看系统内核版本</font>
> `cat /proc/version` : 查看系统内核版本  # CentOS & ubuntu

![系统内核版本](https://img-blog.csdnimg.cn/20201007001905584.png#pic_left)

---
### <font color='red'>查看系统发行版本</font>
> `cat /etc/redhat-release` : 查看系统发型版本  # CentOS

![系统发行版本](https://img-blog.csdnimg.cn/20201007002135120.png#pic_left)


