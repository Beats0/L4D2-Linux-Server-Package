# L4D2-Linux-Server-Package

### 插件配置

此插件是基于Linux的，因为编译问题，所以有的能在Windows上运行的插件不一定能在Linux环境上运行，前提是你能得到 `.dll` 所对应的 `.so`文件

##### 可能需要用到的工具

`PuTTY`

PuTTY是一个Telnet、SSH、rlogin、纯TCP以及串行接口连接软件。较早的版本仅支持Windows平台，在最近的版本中开始支持各类Unix平台

`Xftp`

是一个基于 MS windows 平台的功能强大的SFTP、FTP 文件传输软件。

##### 插件默认配置

`coop` 模式
```
//配置Left 4 Dead 2 Dedicated Server\left4dead2\cfg\server.cfg

// 服务器名称
hostname "L4D2 Bhop Server[Beats0]"

//  coop战役模式，versus对抗模式
sm_cvar mp_gamemode "coop"

// coop战役模式，versus对抗模式
sv_gametypes coop

// 对抗或药抗请访问
// 药抗插件：https://github.com/Stabbath/ProMod
// 药抗整合包：https://github.com/Paubrk/Promod-fully-install-package
```

`多人服务器`
```
//配置Left 4 Dead 2 Dedicated Server\left4dead2\cfg\sourcemod\l4d2_rmc.cfg

// 服务器支持玩家人数设置
// Default: "4"
// Minimum: "1.000000"
// Maximum: "24.000000"
L4D2_Rmc_total "8"
```

`admin管理员`
```
//配置Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\configs\admins_simple.ini

//管理员设置：
"STEAM_1:1:182710453"     "99:z" //Beats0
```
控制台输入status，查看steamid（如STEAM_1:1:111111111）

或者到 https://steamid.io/ 查看自己的steamid

最后一行添加自己的steamid，"STEAM_1:1:11xxxxxxx" "99:z"

注意之间是没有空格符号的，不论前面后面还是里面

#### 插件安装

把文件 `left4dead2` 复制到 `\Steam\steamapps\common\Left 4 Dead 2 Dedicated Server\`

不喜欢的插件就到这个位置删除（对应插件名字）

`Steam\steamapps\common\Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\plugins`

或者到这个位置修改对应的cgf文件内容

`Steam\steamapps\common\Left 4 Dead 2 Dedicated Server\left4dead2\cfg\sourcemod`

##### 插件管理
```
//配置Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\plugins
plugins
     ├─admin-flatfile.smx
     ├─adminhelp.smx
     ├─adminmenu.smx            //!admin 管理员指令
     ├─all4dead2.smx
     ├─antiflood.smx
     ├─basebans.smx
     ├─basechat.smx
     ├─basecomm.smx
     ├─basecommands.smx
     ├─basetriggers.smx
     ├─basevotes.smx
     ├─bhop.smx                 //Bhop连跳，默认开启
     ├─clientprefs.smx          //连接时展示面板
     ├─funcommands.smx          //杂七杂八的娱乐命令
     ├─funvotes.smx             //!vote 投票
     ├─hp.smx                   //!hp 加血控制
     ├─l4d2_infectedbots_fix_ch.smx//智能模式
     ├─l4d2_kill_mvp.smx        //击杀排行面板
     ├─l4d2_more_medical.smx    //多倍补给
     ├─l4d2_showdamage.smx      //显示伤害
     ├─l4d2_tank_hp.smx         //tank血量
     ├─l4d2_WeaponUnlock.smx    //隐藏武器解锁
     ├─l4d2_zisha.smx           //!zs/!kill 自杀
     ├─l4d_gear_transfer.smx    //给予物品
     ├─l4d_infectedhp.smx       //显示血条
     ├─l4d_Rmc.smx              //服务器人数设置
     ├─nextmap.smx              //自动换图
     ├─playercommands.smx       //玩家命令
     ├─reservedslots.smx
     ├─rygive.smx               //!rygive 获取
     ├─R_AC_MAPS.smx            //自动换图
     ├─R_AutoIS.smx             //多特插件
     ├─R_UD_FF.smx              //伤害控制
     └─sounds.smx


//配置Left 4 Dead 2 Dedicated Server\left4dead2\cfg

cfg
├─sourcemod
│     ├─funcommands.cfg
│     ├─l4d2_All4Dead2.cfg
│     ├─l4d2_kill_mvp.cfg
│     ├─l4d2_more_medical.cfg
│     ├─l4d2_rmc.cfg
│     ├─l4d2_tank_hp.cfg
│     ├─l4d2_WeaponUnlock.cfg
│     ├─l4d2_zisha.cfg
│     ├─l4dinfectedbots.cfg
│     ├─l4d_gear_transfer.cfg
│     ├─l4d_infectedhp.cfg
│     ├─R_AC_MAPS.cfg
│     ├─R_AutoIS.cfg
│     ├─R_UD_FF.cfg
│     ├─sm_warmode_off.cfg
│     ├─sm_warmode_on.cfg
│     └─sourcemod.cfg
└─server.cfg
```

##### 服务器启动
```
//配置Left 4 Dead 2 Dedicated Server\start.sh

// 安装screen，用来挂后台服务
apt-get install screen

// 进入start.sh所在的位置
cd /root/Steam/steamapps/common/Left\ 4\ Dead\ 2\ Dedicated\ Server/

// 用screen命令后台启动服务器
screen /root/Steam/steamapps/common/Left\ 4\ Dead\ 2\ Dedicated\ Server/start.sh

// 服务器启动成功后按Ctrl+A,再按D后台服务器挂起即可

// 关于start.sh的内容 ./srcds_run -game left4dead2 -secure +hostport 23333 +map c2m1_highway -condebug +exec server.cfg

// ./srcds_run 就是运行服务端程序 后面跟的都是运行参数
// -game left4dead2 指定游戏为L4D2
// -secure 开启VAC
// +hostport 23333 指定服务器端口为23333
// +map c2m1_highway 默认开始地图
// -condebug 开启记录日志 在left4dead2文件夹下生成console.log的记录文件
// +exec server.cfg 加载server.cfg
```

##### 常遇问题
----------------------------------------------

 1. 出现mod冲突？
 - 房主建房前控制台输入 `sv_consistency 0` 回车

 2. 显示房主不在不可加入游戏中或者只能进去4个人或者无限加载？
 - 房主邀请，或者重新开房；还是不行？本插件与你无缘

 3. 特感太多？
 - 在多特插件`l4dinfectedbots.cfg` 对应cfg文件里设置特感数目<br>
 或者直接删除`l4d2_infectedbots_fix_ch`该插件,不喜欢的插件就到这个位置删除（对应插件名字）
`Steam\steamapps\common\Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\plugins`

 4. 其他问题......建议等死_(:3/L)\		（百度谷歌或者问问其他老司机）

#### 其他参考
 - [贴吧：[教程]猴子都能看懂的服务器架设教程(Linux限定)](https://tieba.baidu.com/p/4783601071?red_tag=0795345647)
 - [药抗插件：Stabbath/ProMod](https://github.com/Stabbath/ProMod)
 - [药抗整合包：Paubrk/Promod-fully-install-package](https://github.com/Paubrk/Promod-fully-install-package)
 - [服务器启动管理：mvandorp/server-config](https://github.com/mvandorp/server-config)

#### 我的服务器(Bhop server)
connect 47.94.16.206:23333
