# 配置本地yum源

1. 在虚拟机(服务器)中添加iso镜像
   
   [ VirtualBox中配置linux OS的本地磁盘镜像作为其软件源_kexianmiao的专栏-CSDN博客](https://blog.csdn.net/kexianmiao/article/details/52413382)
   
   ![](D:\Documents\Oracle运维实战\assets\2021-11-30-10-01-08-image.png)

2. 建立挂载目录
   
   ```shell
   mkdir /mnt/cdrom
   ```

3. 挂载镜像
   
   ```shell
   # 查看镜像挂载在那个盘
   lsblk
   
   # 挂载到文件夹
   mount /dev/sr1 /mnt/cdrom
   ```

4. 备份原本的yum源文件
   
   ```shell
   vim /etc/yum.repos.d/redhat.repo
   
   #[163]
   #name=163
   #baseurl=http://mirrors.163.com/centos/7/os/x86_64
   #gpgcheck=0
   #enabled=1
   ```

5. 建立本地源文件
   
   ```shell
   vim /etc/yum.repos.d/local.repo
   
   # 配置内容
   [local]
   name=local
   baseurl=file:///mnt/cdrom
   gpgcheck=1
   enabled=1
   gpgkey=file:///mnt/cdrom/RPM-GPG-KEY-redhat-release
   ```

6. 加载本地源
   
   ```shell
   # 清除yum源
   yum clean all
   
   # 缓存本地源
   yum makecache
   
   # 测试
   yum repolist all 
   ```

![](D:\Documents\Oracle运维实战\assets\a900036516d9f4c42d682e7a424ffdfb6e85d6da.png)

7. 开机自动挂载
   
   ```shell
   vim /etc/fstab
   ```

   /dev/sr1 /mnt/cdrom iso9660 defaults 0 1

```

```
