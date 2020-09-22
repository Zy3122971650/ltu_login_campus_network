# 辽宁工程技术大学校内登录校园网脚本

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
由于对js/html/css不熟悉，所以有些参数不知道从哪来的，比如ac_id和double_stake
其他的参数有空再写，所web认证中所需要的js脚本已在仓库中，可自行查看。

## 当前功能

功能很单一，只有登录校园网。

## TODO
- [ ] 保持登录