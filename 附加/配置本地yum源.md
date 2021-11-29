# 配置本地yum源

1. 在虚拟机(服务器)中添加iso镜像
   
   ![](file://D:%5CDocuments%5Cassets%5C2021-11-29-15-41-30-image.png)

2. 建立挂载目录
   
   ```shell
   mkdir /mnt/cdrom
   ```

3. 挂载镜像
   
   ```shell
   mount /dev/cdrom /mnt/cdrom
   ```

4. 备份原本的yum源文件
   
   ```shell
   cd /etc/yum.repos.d
   mkdir bak
   mv * bak/
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
   yum repolist all ![](D:\Documents\assets\2021-11-29-15-49-00-image.png)
   ```

![](D:\Documents\assets\2021-11-29-15-49-08-image.png)
