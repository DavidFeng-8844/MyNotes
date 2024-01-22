
查看有无 yum安装包 ，有的话卸载：

查看：rpm -qa |[grep](https://so.csdn.net/so/search?q=grep&spm=1001.2101.3001.7020) yum

卸载：rpm -aq|grep yum|xargs rpm -e --nodeps



>Check Version

```
cat /etc/redhat-release
```

>CentOS 9.2 

```
https://mirrors.aliyun.com/rockylinux/9.2/AppStream/x86_64/os/
```
>Base:

```
https://mirrors.aliyun.com/rockylinux/9.2/BaseOS/x86_64/os/
```