## linux系统管理
### 进程管理
- 判断服务器健康状态
-  top [选项]
   
*** 
    
 ### 查看系统所有进程
    >ps aux（BSD）

    > ps -le（linux标准命令格式）
    
        - %MEN：该进程占用的物理内存的百分比
        -  VSZ： 该进程占用虚拟内存的大小
        -  RSS：该进程占用的实际物理内存的大小
        -  TTY：该进程是在哪个终端运行的。其中tty1-tty7代表本地控制台终端，tty1-tty6是本地的字符界面终端，tty7是图形终端。pst/0-255代表虚拟终端
         - STAT:进程状态。常见状态有：R:运行、S：睡眠、T：停止状态、s:包含子进程、+：位于后台
         - START:该进程的启动时间
         - TIME:该进程占用CPU的运算时间
         - COMMAND:产生该进程的命令名
        
*** 
### 杀死进程
    *  kill -l
        - SINGUP(1) 该信号让进程立即关闭，然后重新读取配置文件之后重启
        - SIGINT(8) 程序终止信号，用于终止前台应用。相当于ctrl+c
        - SIGFPE(3) 发生致命的算术运算错误时发出
        - SIGKILL(9) 用来立即结束程序的运行
    * 例子：
        - kill -1 [PID] (重启进程)
        - kill -9 [PID] (强制杀死进程)

***
### linux工作管理
**例子：tar -zvf etc.tar.gz /etc &**&&**命令的执行过程中，按下ctrl+z**
- 查看后台的工作
    * jobs -l
- 将后台暂停的工作恢复到前台执行
    * fg %工作号                      （**注意与PID的区别**）

**后台恢复执行的命令，是不能和前台有交互的，否则不能恢复到后台执行**

***
### 系统资源的查看
- vmstat[刷新延时 刷新次数]
    + 例子：vmstat 1 3
- dmesg开机时内核检测信息
    + 例子：dmesg && dmesg | grep CPU
- free命令查看内存使用状态
    + free [-b|-k|-m|-g]
    + 选项
        * -b：以字节为单位显示
        * -k:以KB
        * -m：以MB
        * -g：以GB

**缓存(cache)是用来加速数据从硬盘中读取；而缓冲(buffer)是用来加速数据写入硬盘的**

- 查看CPU信息
    + cat /proc/cpuinfo
- uptime命令 #显示系统的启时间和平均负载，也就是top命令的第一行。w命令也可以看到这个数据
- 查看系统与内核相关信息
    + -a：查看系统所有相关信息
    + -r：查看内核版本
    + -s：查看内核名称
- 判断当前系统位数
    + file /bin/ls
- 查询当前linux版本
    + lsb_release -a
- 列出进程打开或使用的文件信息
    + lsof [选项]
        * 选项
            * -c字符串
            * -u用户名
            * -p pid
        
***
### 系统定时任务
> service crond restart

> chkconfig crond on

- crontab [选项]
    + 选项：
        + -e：编辑定时任务
        + -l：查询crond定时任务
        + -r：删除当前用户所有的crond任务
            
