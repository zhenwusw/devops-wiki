# devops-wiki


* 快速打印出本机 IP 地址
`ifconfig | perl -nle'/(\d+\.\d+\.\d+\.\d+)/ && print $1'`


* A modern, browser-based frontend to gdb 
https://github.com/cs01/gdbgui#screenshots


* `ps aux | grep go`, shell 为每个命令都创建了一个进程，然后把左边的命令的标准输出用管道与右边的命令的标准输入连接起来。

