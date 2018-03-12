# L4D2-Linux-Server-Package

### 插件配置

此插件是基于Linux的，因为编译问题，所以有的能在Windows上运行的插件不一定能在Linux环境上运行，

使用拓展人数环境：[left4downtown2-v0.5.4.2](https://forums.alliedmods.net/showpost.php?p=2286832&postcount=758)

使用拓展人数插件(默认12人，最大32人)：[ABM：MultiSlots/SuperVersus Alternative](https://forums.alliedmods.net/showthread.php?t=291562),配置详见：https://gitlab.com/vbgunz/ABM

##### 可能需要用到的工具

`PuTTY` PuTTY是一个Telnet、SSH、rlogin、纯TCP以及串行接口连接软件。较早的版本仅支持Windows平台，在最近的版本中开始支持各类Unix平台

`Xftp` 是一个基于 MS windows 平台的功能强大的SFTP、FTP 文件传输软件

注意Xftp的使用必须是以自己的时区为准，当初因为hammer editor必须要使用美国时区，所以一直不能安装，差点被坑死，后来换成自己的所在时区就行了

##### 插件默认配置

`coop` 模式
```shell
//配置Left 4 Dead 2 Dedicated Server\left4dead2\cfg\server.cfg

// 服务器名称
hostname "L4D2 Bhop Server[Beats0]"

// versus 对抗模式
// mutation或者community设定为突变模式，
// 模式类型详见 https://tieba.baidu.com/p/2276230914?red_tag=3505874637
// 如 
//sm_cvar mp_gamemode "mutation4"
//sv_gametypes mutation4

sm_cvar mp_gamemode "coop"
sv_gametypes coop

// realism 写实模式
// survival 生存模式
// scavenge 清道夫模式
// teamscavenge 团队清道夫模式
// teamversus 团队对抗模式

// 对抗或药抗请访问
// 药抗插件：https://github.com/Stabbath/ProMod
// 药抗整合包：https://github.com/Paubrk/Promod-fully-install-package
```


`admin管理员`
```shell
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
```shell
//配置Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\plugins
plugins
     ├─abm.smx                  //人数拓展程序
     ├─admin-flatfile.smx
     ├─adminhelp.smx
     ├─adminmenu.smx            //!admin 管理员指令
     ├─all4dead2.smx            //造物插件
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
     ├─14d2.info.smx            //连接信息显示及黑白提示
     ├─l4d2_kill_mvp.smx        //击杀排行面板
     ├─l4d2_more_medical.smx    //多倍补给
     ├─l4d2_showdamage.smx      //显示伤害
     ├─l4d2_tank_hp.smx         //tank血量
     ├─l4d2_WeaponUnlock.smx    //隐藏武器解锁
     ├─l4d2_zisha.smx           //!zs/!kill 自杀
     ├─l4d_gear_transfer.smx    //电脑自动传递物品
     ├─l4d_infectedhp.smx       //显示血条
     ├─l4dafkfix.smx            //debug服务器人数设置
     ├─nextmap.smx              //自动换图
     ├─playercommands.smx       //玩家命令
     ├─reservedslots.smx
     ├─rygive.smx               //!rygive 获取
     ├─R_AC_MAPS.smx            //自动换图
     ├─R_AutoIS.smx             //多特插件
     ├─R_MA.smx                 //debug 解决人物混乱的问题
     ├─R_UD_FF.smx              //伤害控制
     └─sounds.smx


//配置Left 4 Dead 2 Dedicated Server\left4dead2\cfg

cfg
├─sourcemod
│     ├─abm.cfg                 人数拓展配置  详见 https://forums.alliedmods.net/showthread.php?t=291562
│     ├─funcommands.cfg
│     ├─l4d2_All4Dead2.cfg
│     ├─l4d2_kill_mvp.cfg
│     ├─l4d2_more_medical.cfg
│     ├─l4d2_tank_hp.cfg
│     ├─l4d2_WeaponUnlock.cfg
│     ├─l4d2_zisha.cfg
│     ├─l4dinfectedbots.cfg
│     ├─l4d_gear_transfer.cfg
│     ├─l4d_infectedhp.cfg
│     ├─R_AC_MAPS.cfg
│     ├─R_AutoIS.cfg
│     ├─R_MA.cfg
│     ├─R_UD_FF.cfg
│     ├─sm_warmode_off.cfg
│     ├─sm_warmode_on.cfg
│     └─sourcemod.cfg
└─server.cfg
```

##### 涉及指令
```shell
// say
!admin              管理员指令
!zs/!kill           自杀
!rygive             管理员指令
!jg/!joingame	    加入游戏
!away               旁观

// addbot 更多abm插件命令详见 https://gitlab.com/vbgunz/ABM
!abm-mk 4 2         添加4个boot
!abm-mk -16 2       使用16个boot
!kb                 剔除bot
!hp                 回血指令

// 调整人数:

!sm_cvar sv_maxplayers "12"
!sm_cvar sv_visiblemaxplayers "12"
```

##### 服务器启动
```shell
//配置Left 4 Dead 2 Dedicated Server\start.sh

// 安装screen，用来挂后台服务
apt-get install screen

// 进入start.sh所在的位置
cd /root/Steam/steamapps/common/Left\ 4\ Dead\ 2\ Dedicated\ Server/

// 用screen命令后台启动服务器
screen ./start.sh

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

 3.不喜欢的插件就到这个位置删除（对应插件名字）
 
 - `Steam\steamapps\common\Left 4 Dead 2 Dedicated Server\left4dead2\addons\sourcemod\plugins`

 4. 用 `screen` 命令有时候服务器进程可能任然会死掉，建议平时多检查服务器是否还在运行，如果死掉了就kill掉进程再重开

 5. 其他问题......建议等死_(:3/L)\		（百度谷歌或者问问其他老司机）

#### 其他参考
 - [贴吧：[教程]猴子都能看懂的服务器架设教程(Linux限定)](https://tieba.baidu.com/p/4783601071?red_tag=0795345647)
 - [药抗插件：Stabbath/ProMod](https://github.com/Stabbath/ProMod)
 - [药抗整合包：Paubrk/Promod-fully-install-package](https://github.com/Paubrk/Promod-fully-install-package)
 - [服务器启动管理：mvandorp/server-config](https://github.com/mvandorp/server-config)
 - [插件汉化by望夜](http://bbs.3dmgame.com/forum.php?mod=viewthread&tid=4920489&page=8&authorid=778835)
 - [bilibili 兔子整理及视频](https://www.bilibili.com/video/av5466730/)
 - [插件论坛 alliedmods.net](https://forums.alliedmods.net/)

#### 我的服务器(Bhop server)

connect 47.94.16.206:23333

status 2018-02-06————2019-02-06

最后提醒一下，开服务器确实简单，但要让服务器活下去就不好说了，因为总有人搞事情，总有人DDos攻击你的服务器，呵呵