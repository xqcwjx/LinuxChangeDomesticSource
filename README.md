# Linux更改为国内源

## 目录：

**1.ubuntu**

**2.centos**

**3.kali**

- ### ubuntu修改默认源为国内源

  1. 备份/etc/apt/sources.list  &&  备份 cp /etc/apt/sources.list /etc/apt/sources.list.bak

  2. 打开/etc/apt/sources.list文件的命令

     ```
     sudo vi /etc/apt/sources.list
     ```

  3. 在/etc/apt/sources.list文件前面添加如下条目、可以添加阿里源、中科大源、163源、清华源等等......

     **阿里源**

     ```
     deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
     deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
     deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
     deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
     deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
     deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
     deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
     deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
     deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
     deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
     ```

     **中科大源**

     ```
     deb https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
     deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
     deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
     deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
     deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
     deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
     deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
     deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
     deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
     deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
     ```

     **163源**

     ```
     deb http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
     deb http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
     deb http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
     deb http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
     deb http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
     deb-src http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
     deb-src http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
     deb-src http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
     deb-src http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
     deb-src http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
     ```

     **清华源**

     ```
     deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
     deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
     deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
     deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
     deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
     deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
     deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
     deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
     deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
     deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
     ```

  4. wq保存以后，最后执行如下命令更新源

     ```
     sudo apt-get update
     sudo apt-get upgrade
     ```

- ### centos修改默认源为国内源

  1. 备份（针对所有Centos可用，备份文件在当前路径下）

     ```
     mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
     ```

  2. 下载新的CentOS-Base.repo 到/etc/yum.repos.d/

     Centos5、6、7等等...通用 修改代码块最后面的Centos-5.repo、Centos-6.repo、Centos-7.repo就可以了，源可以可以这样修改 修改前：http://mirrors.aliyun.com/修改后：http://XXX.XXX/修改成上的自己喜欢的就可以

     ```
     wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
     ```

     或者

     ```
     curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
     ```

  3. 之后运行yum makecache生成缓存

     ```
     yum makecache
     ```

- ### kali修改默认源为国内源

  1. 备份/etc/apt/sources.list  &&  备份 cp /etc/apt/sources.list /etc/apt/sources.list.bak

  2. 打开/etc/apt/sources.list文件的命令

     ```
     sudo vi /etc/apt/sources.list
     ```

  3. 在/etc/apt/sources.list文件前面添加如下条目、可以添加阿里云、中科大、清华大学、浙大、东软大学、官方源等等......

     **阿里云**

     ```
     deb http://mirrors.aliyun.com/kali kali-rolling main non-free contrib
     deb-src http://mirrors.aliyun.com/kali kali-rolling main non-free contrib
     ```

     **中科大**

     ```
     deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
     deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
     ```

     **清华大学**

     ```
     deb http://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free
     deb-src https://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free
     ```

     **浙大**

     ```
     deb http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free
     deb-src http://mirrors.zju.edu.cn/kali kali-rolling main contrib non-free
     ```

     **东软大学**

     ```
     deb http://mirrors.neusoft.edu.cn/kali kali-rolling/main non-free contrib
     deb-src http://mirrors.neusoft.edu.cn/kali kali-rolling/main non-free contrib
     ```

     **官方**

     ```
     deb http://http.kali.org/kali kali-rolling main non-free contrib
     deb-src http://http.kali.org/kali kali-rolling main non-free contrib
     ```

  4. 这样源就切换了然后就是

     ```
     apt-get update
     apt-get upgrade
     apt-get dist-upgrade
     ```


