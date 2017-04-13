**yum**

```
# yum -y install epel-release

# yum -y install *

# yum -y groupinstall '*'
```

yum默认下载目录：`/var/cache/yum/x86_64/[centos/fedora-version]/[repository]/packages`

只下载，不安装：

```
# yum install --downloadonly --downloaddir=下载路径 *

专门包下载工具：yumdownloader(下载到当前目录，不下载依赖包)
# yum -y install yum-utils
# yumdownloader
```
