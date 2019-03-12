## 常用系统工作命令
1. **echo**
    - echo [字符串 | $变量]
    - 在终端上输出字符串或变量的值
  
2. **date**
    - date [OPTIONS] ["+FORMAT"]
    - 按照指定格式输出系统时间或日期
    - 常用格式化参数
  
**参数** | **作用**
-- | --
%t | Tab
%H | 小时（00~23）
%I | 小时（00~12）
%M | 分钟（00~59）
%S | 秒（00-59）
%j | 一年中的第几天

3. **reboot**
    - 重启系统

4. **poweroff**
    - 关闭系统

5. **wget**
    - wget [OPTIONS] ADDRESS
    - 在终端中下载网络文件
    - 常用参数
  
**参数** | **作用**
-- | --
-b | 后台模式下载
-P | 下载到指定目录
-t | 最大尝试次数
-c | 断点续传
-p | 下载页面内所有资源 包括图片视频等
-r | 递归下载

6. **ps**
    - 查看系统中当前的进程状态
    - 常用ps -ef 和 ps aux 推荐使用ps -ef
    - ps aux 和 ps -aux 有所区别
    - Linux系统进程状态a
      - R（运行）：进程正在运行或在运行队列中等待
      - S（中断）：进程处于休眠中 当某个条件形成或者接收到信号后则脱离该状态
      - D（不可中断）：进程不响应系统异步信号 即使使用kill命令也不能将其中断
      - Z（僵死）：进程已经终止 但进程描述符依然存在 直到父进程调用wait4()系统调用后进程释放
      - T（停止）：进程收到停止信号后停止运行

 7. **top**
    - 动态监视进程活动和系统负载信息
  
 8. **pidof**
    - 查询某个服务进程的PID值
  
 9. **kill**
    - kill [OPTIONS] PID
    - 终止指定的服务进程

 10. **killall**
     - 终止指定服务的所有进程
     
 ## 工作目录命令
 1. **pwd** 
    - 显示当前工作目录
 
 2. **cd**
    - cd [DIR]
    - 切换到指定工作路径
 3. **ls**
    - ls [OPTION] [DIR]
    - -a 查看全部文件 包括隐藏文件
    - -l 查看文件大小属性等详细信息
 4. **mkdir**
    - 创建空白目录 mkdir [OPTION] DIRNAME
    - -p选项按照层次关系创建嵌套的文件目录
 5. **touch**
    - 创建空白文件 touch [OPTION] FILENAME
    - 亦可用于修改已经存在的文件的时间信息
 6. **cp**
    - 用于文件和目录的复制 cp [OPTIONS] SRC DST
    - -p   保留原始文件的属性
    - -d   若对象为“链接文件”，则保留该“链接文件”的属性 -r   递归持续复制(用于目录)
    - -i   若目标文件存在则询问是否覆盖
    - -a   相当于-pdr(p、d、r 为上述参数)
 7. **mv**
    - 用于剪切文件或重命名文件 mv [OPTIONS] SRCFILE DSTDIR|DSTFILE
 8. **rm**
    - 删除文件或空白目录 rm [OPTION] DIR|FILE
    - -f 强制删除 跳过是否删除的确认
    - -r 递归删除 用于删除飞空的目录
 9. **dd**
    - 用于按照指定大小和个数的数据块来复制文件或转换文件
## 文本查看命令
 1. **cat**
    - 查看(内容较少的)文本文件
    - -n 显示行号
    - **tac**命令从尾到头显示文件
 2. **more**
    - 查看(内容较多的)文本文件 下方显示内容百分比
    - Space/Enter向下翻页
 3. **head**
    - 查看纯文本文件的前几行
    - -n选项指定查看的行数
 4. **tail**
    - 查看纯文本文件的最后几行
    - -n选项指定查看的行数
    - -f选项实时跟踪显示文件的变化
 5. **tr**
    - 替换文本文件的类容 tr [原字符串] [替换字符串] 如 tr [a-z] [A-Z]将文本文件转换为大写字符表示
 6. **wc**
    - 用于统计指定文件的行数、词数和字节数
    - -l 统计行数
    - -w 统计词数
    - -c 统计字节数
 7. **stat**
    - 查看文件的具体存储信息和时间等信息
 8. **cut**
    - 按列提取文本字符 如 `cut -d: -f1 /etc/passwd`表示查看以‘:’为列分隔符的第一列
    - -d 指定列间隔符号
    - -f 指定查看第几列
 9. **diff**
    - 用于比较多个文本文件的差异
    - --brief选项显示是否相同的结果
    - -c选项显示详细的差异信息
 10. **file**
    - 用于查看文件的类型
## 系统状态命令
 1. **ifconfig**
    - 获取网卡配置与网络状态等信息
 2. **uname**
    - 用于查看系统内核与系统版本等信息，格式为“uname [-a]”
 3. **uptime**
    - 查看系统的负载信息
    - 显示当前系统时间、系统已运行时间、启用终端数量以 及平均负载值等信息
    - 平均负载值指的是系统在最近 1 分钟、5 分钟、15 分钟内的压力情况;负载值越低越好，尽量不要长期超过1，在生产环境中不要超过5
 4. **free**
    - 显示当前系统中内存的使用量信息，格式为“free [-h]”
 5. **who**
    - 查看当前登入主机的用户终端信息
 6. **last**
    - 查看所有系统的登录记录
 7. **history**
    - 显示历史执行过的命令，格式为“history [-c]”
    - 自定义/etc/profile 文件中的 HISTSIZE 变量值可配置记录的历史命令的条数
    - -c参数会清空所有的命令历史记录
    - 可以使用“!编码数字”的方式来重复执行某一次的命令
 8. **sosreport**
    - 收集系统配置及架构信息并输出诊断文档
## 压缩与搜索命令
 1. **tar**
    - 用于对文件进行打包压缩或解压，格式为tar [OPTION] [FILE...]
    - 一般使用`tar -czvf`把指定的文件进行打包压缩，相应的解压命令为`tar-xzvf`

**参数** | **作用**
-- | --
-c | 创建压缩文件
-x | 解开压缩文件
-t | 查看压缩包内有哪些文件 
-z | 用Gzip压缩或解压
-j | 用bzip2压缩或解压
-v | 显示压缩或解压的过程
-f | 目标文件名
-p | 保留原始的权限与属性 
-P | 使用绝对路径来压缩
-C | 指定解压到的目录
 
 2. **grep**
    - 基于正则表达式在文本中执行关键词搜索
    - -n 参数用来显示搜索到信息的行号
    - -v 参数用于反选信息(即没有包含 关键词的所有信息行)
 3. **find**
    - 按照指定条件来查找文件,find [DIR] COND OP”，例如`find /etc -name "host*"`查找/etc目录下所有以host开头的文件列表
    
    
**参数** | **作用**
----------------------- | --
GPL ICMP_INFO PING \*NIX | 3745
GPL ICMP_INFO PING BSDtype | 528
ET INFO Session Traversal Utilities for NAT (STUN Binding Response) | 124
GPL SCAN superscan echo | 120
ETN AGGRESSIVE IPs | 48
ET SCAN Suspicious inbound to mySQL port 3306 | 48
GPL ICMP_INFO PING BayRS Router | 9
GPL ICMP_INFO PING Flowpoint2200 or Network Management Software | 9
ET SCAN Suspicious inbound to MSSQL port 1433 | 8
ET SCAN Potential VNC Scan 5900-5920 | 7
ET SCAN Suspicious inbound to PostgreSQL port 5432 | 6
ET SCAN Potential VNC Scan 5800-5820 | 2
ET SCAN HID VertX and Edge door controllers discover | 2
ET SCAN Potential SSH Scan | 2
ET SCAN Suspicious inbound to Oracle SQL port 1521 | 2
ET SCAN Rapid POP3 Connections - Possible Brute Force Attack | 1
ET DNS DNS Lookup for localhost.DOMAIN.TLD | 1
