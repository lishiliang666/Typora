# 使用 vue 创建 electron 项目

来源 

```shell
https://www.bilibili.com/video/BV1Ua4y1x7VE?p=2
```



## 一： 开发环境配置

### 第一步创建 test 项目

```js
vue create test
```

### 第二步 安装插件  electron-builder

```shell
cd test
vue add electron-builder
```

#### 2.1    在安装 electron-chromedriver 时  会卡死

解决方案 ：  暂停   到 electron taobao  里找到对应的版本  找到压缩包和配置文件 

然后下载到 electron 默认安装文件里

```js
// 第一次卡死
electron-chromedriver@5.0.1 install D:\123\electron01\test\node_modules\electron-chromedriver
```

打开 electron 文件下载路径

```js
C:\Users\14465\AppData\Local\electron\Cache
```

打开浏览器 搜索  electron taobao  打开淘宝镜像

找到 5.0.1 版本  找到 electron-chromedriver 

下载下面两个文件  下载到 上面的那个路径里  将原文件删除

```shell
chromedriver-v5.0.1-win32-x64.zip
SHASUMS256.txt
// 修改 SHASUMS256.txt 后缀名
SHASUMS256.txt-版本号   
```

修改完该路径下的文件为

```shell
chromedriver-v5.0.1-win32-x64.zip
SHASUMS256.txt-5.0.1
```

Ctrl + C  退出运行  然后再重新安装

```shell
vue add electron-builder
```



#### 2.2 在安装 electron时  会卡死第二次卡死

```js
// 第二次卡死
Downloading tmp-18056-0-electron-v6.1.12-win32-x64.zip
```

解决方案  再淘宝镜像找到 6.1.12

找到 electron  压缩包  和 配置文件  仍然下载到 electron 路径里

```shell
electron-v6.1.12-win32-x64.zip
SHASUMS256.txt
//  修改后缀名  删除原压缩包
```

最后该路径下 共有4个文件

```shell
chromedriver-v5.0.1-win32-x64.zip
electron-v6.1.12-win32-x64.zip
SHASUMS256.txt-5.0.1
SHASUMS256.txt-6.1.12
```

Ctrl + C 退出进程  在执行

```shell
vue add electron-builder
// 然后执行
npm run electron:serve
```

#### 2.3 报错  

```shell
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! test@0.1.0 electron:serve: `vue-cli-service electron:serve`
npm ERR! Exit status 1
```



解决方案   删除 test 项目  重修创建 test 项目  依次执行以下代码

```shell
vue create test
cd test
vue add electron-builder
vue run electron:server 

// 执行成功   弹出 test 窗口
```



## 二：生产环境配置

```shell
// 再开发环境的基础上 执行
vue run electron:build
```

再次卡死

```shell
downloading     url=https://github.com/electron-userland/electron-builder-binaries/releases/download/winCodeSign-2.5.0/winCodeSign-2.5.0.7z size=5.6 MB parts=1
```

解决方案

打开对应 github 地址

```shell
https://github.com/electron-userland/electron-builder-binaries/
```

点击 releases 找到对应版本 winCodeSign-2.5.0

点击 Assets   下载 Source code (zip)   // 源码

打开 electron 生产环境下地址

```shell
C:\Users\14465\AppData\Local\electron-builder\Cache\winCodeSign
```

将 Source code (zip) 下载到这个文件里







