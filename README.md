# devops-wiki


快速打印出本机 IP 地址

`ifconfig | perl -nle'/(\d+\.\d+\.\d+\.\d+)/ && print $1'`
