# unidbg-fetch-qsign

获取QQSign通过Unidbg

## 安装java
**• 下载并安装适用于自己系统的jdk或jre https://bell-sw.com/pages/downloads/**

## 1.1.0版使用流程
**• 获取qsign(二选一)**
1. 克隆文件: `git clone --depth=1 -b 1.1.0 https://gitee.com/KudouShinnyan/qsign.git`
2. 直接下载zip然后解压https://gitee.com/KudouShinnyan/qsign/repository/archive/1.1.0.zip

**• 从device.json文件查看并复制android id**

gocq直接在运行的目录就能找到文件

Yunzai 3.0是在Yunzai目录的data/device.json

Miao-Yunzai是在Yunzai目录的data/icqq/QQ号/device.json

把android id复制下来, 后面的 "某某id" 改成你复制的id

假如用1.1.0版使用多个只因器人也许要把android id改成一样的


**• 启动qsign**
1. 用终端或CMD进去qsign目录
2. 执行这个: `bin/unidbg-fetch-qsign --host=0.0.0.0 --port=8081 --count=1 --library=txlib/8.9.63 --android_id=某某id` (CMD就不要用bash了)  

**• 修改文件**

gocq的话可以用1.1.0版, 的gocq, 要修改的文件是gocq运行目录的config.yml文件, 假如文件是由旧版生成的那就删了重新生成, 然后编辑文件把没注释掉的sign-server右边单引号里的横杠改成`http://127.0.0.1:8081` , 改完之后启动gocq就是了

Yunzai 3.0或Miao-Yunzai的话是在Yunzai目录的config/config/bot.yaml文件, 在最后面插入一行`sign_api_addr: http://127.0.0.1:8081/sign` , 已有这一行的话就直接修改, icqq用0.4.10版, 完成之后启动Yunzai就是了

## 1.1.9版使用流程
**• 获取qsign(二选一)**
1. 克隆文件: `git clone --depth=1 -b 1.1.9 https://gitee.com/KudouShinnyan/qsign.git`
2. 直接下载zip然后解压https://gitee.com/KudouShinnyan/qsign/repository/archive/1.1.9.zip

(1.2.1版的流程应该差不多但貌似不兼容arm的系统)  

**• 启动qsign(不再需要android id)**
1. 用终端或CMD进去qsign目录
2. 假如txlib里没有你要的QQ版本那就删掉txlib目录然后`git clone --depth=1 -b txlib https://gitee.com/KudouShinnyan/qsign.git ./txlib`
3. 执行这个: `bash bin/unidbg-fetch-qsign --basePath=txlib/某某QQ版本` (CMD就不要用bash了)  

**• 修改文件**

gocq的话是用1.2.0版的gocq, 要修改的文件是gocq运行目录的config.yml文件, 假如文件是由旧版生成的那就删了重新生成, 然后编辑文件把没注释掉的sign-server项下边url单引号里的横杠改成`http://127.0.0.1:8081` , 然后在protocol分支找到需要的版本,复制 "原始数据" 的链接并下载, 放进gocq运行目录的data/versions,安卓爪机改名为1.json, 安卓平板改名为6.json, 完成后启动gocq就是了

Yunzai 3.0或Miao-Yunzai的话是在Yunzai目录的config/config/bot.yaml文件, 在最后面插入一行`sign_api_addr: http://127.0.0.1:8081/sign?key=114514` , 已有这一行的话就直接修改, icqq用最新版, 完成之后启动Yunzai就是了  
