# 使用宝塔+docker部署ZFile个人网盘

## 项目地址 [zhaojun1998/zfile: 在线云盘、网盘、OneDrive、云存储、私有云、对象存储、h5ai (github.com)](https://github.com/zhaojun1998/zfile)

### 用宝塔安装docker

![安装docker](https://qncdn.laufan.cn/img/20210601193210.png?imageView2/0/q/75%7Cimageslim)

### 镜像加速（可选）

国内服务器拉取镜像速度慢，使用阿里云镜像加速器

登录阿里云[容器镜像服务控制台](https://cr.console.aliyun.com/),在左侧导航栏选择**镜像工具** > **镜像加速器**，复制**加速器地址**

> 官方提示：目前由于Docker Hub限制，导致使用镜像加速器后无法获取最新官方镜像。请暂时去掉加速器配置，直接连接Docker Hub获取。（可以通过修改标签获取最新镜像）

![加速器](https://qncdn.laufan.cn/img/20210601195529.png?imageView2/0/q/75%7Cimageslim)

### 获取镜像

ZFile官方镜像：[zhaojun1998/zfile (docker.com)](https://hub.docker.com/r/zhaojun1998/zfile)

镜像名称中填写 `zhaojun1998/zfile `，再点击获取镜像（默认获取最新镜像）

> 如果不是最新版镜像，请自己到上面地址查看最新版本号，镜像名称中填写`zhaojun1998/zfile:3.1` ，3.1替换为最新版本号

![获取镜像](https://qncdn.laufan.cn/img/20210601193755.png?imageView2/0/q/75%7Cimageslim)

### 创建容器

#### 端口映射

​	添加8080端口

#### 目录映射

​	/root/.zfile/db	/root/zfile/db

​	/root/.zfile/logs	/root/zfile/logs

> 注意：带点的填左边，不带点的填右边
>
> 后续升级的时候只需填好映射，不用重新配置ZFile

其他默认即可

配置如下图

![配置](https://qncdn.laufan.cn/img/20210601192641.png?imageView2/0/q/75%7Cimageslim)

### 反向代理

在宝塔中添加一个网址并绑定、解析好域名，点击设置

如下图顺序点击，填写目标URL，其余默认

> 如果需要添加SSL，请先申请并部署证书（反向代理会导致申请证书失败）

![反向代理](https://qncdn.laufan.cn/img/20210601201050.png?imageView2/0/q/75%7Cimageslim)

### 初始化安装ZFile

如果有SSL，访问 `https://你的域名/#/install`

没有SSL，访问`http://你的域名/#/install`

按提示输入，安装完成

ZFile后台 `https://你的域名/#/admin`

ZFile主页 `https://你的域名/#/main`