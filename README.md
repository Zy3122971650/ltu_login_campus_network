# 辽宁工程技术大学校内登录校园网脚本

## 使用
### 修改参数
打开ltu_router.py修改你的`登录账号`和`密码`和`acid参数`，葫芦岛校区为4，其他校区需要自行查看（通过登录时候抓包查看参数）

### 运行
执行`python3 ltu_router.py`脚本即可，其他js是从校园网拉下来做分析的。

## 依赖
利用pyexcejs库来执行js代码

js环境是由nodejs提供的


所以理论上依赖的安装命令为
```
pip3 install pyexcejs
sudo pacman -S nodejs #根据你的系统来
```
## 用途
让那些没有图形界面的Linux设备可以接入校园网，比如树莓派。

## 设备
目前使用`ip addr`命令来获得本机ip地址，如用其他不支持该命令的系统和设备，自行重写`get_ip`函数 
## 注意
由于当我测试树莓派的时候，发现我的树莓派坏了 - - 所以当前只在我的marjoram上测试通过，测试方法是：伪造另一个MAC地址登录校园网，然后打开任意网页测试，无网络。接着使用脚本进行模拟登录，打开上一网页，网络联通。

## 参数说明
由于对js/html/css不熟悉，所以有些参数不知道从哪来的，比如double_stake
其他的参数有空再写，所web认证中所需要的js脚本已在仓库中，可自行查看。

|参数|说明|
|---|---| 
|acid|似乎是用来区分校区的，不正确会引发BAS错误（葫芦岛校区为4）|
|username|用户名|
|password|密码|
|ip|dhcp分配的ip地址|
|os|操作系统|
|name|也是操作系统相关|
|double_stack|不知道|
|action|操作登录（login）/注销（logout）|
|type|固定值：1|
|info|更安全？操作变形了一番|
|chksum|验算，防止篡改参数|
|_|unix标准时间戳|
|n|固定值：200|
|enc|固定值：srun_bx1|
|hmd5|为了安全！|


## 当前功能

功能很单一，只有登录校园网。

## TODO
- [ ] 保持登录

## 其他奇奇怪怪的东西（小博客）
直接执行该脚本，返回的错误竟然是时间戳错误 - - 应该是用户名密码错误吧- - 害得我排查时间戳排查了好久，不过好像服务器的时间戳确实要慢8min，但这不碍事，应该是和token的过期时间有关系，只要token不过期就可以了。

## 声明
本脚本出于技术交流和方便无web的设备连入本校校园网的目的放至github，请勿用于非法用途，一切法律后果自行承担。