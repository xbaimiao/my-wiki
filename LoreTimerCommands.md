---
title: 判断物品lore定时命令
description: 
published: true
date: 2023-04-22T05:19:56.004Z
tags: 我的世界插件
editor: markdown
dateCreated: 2022-09-01T06:17:09.078Z
---

# 快速开始(LoreTimerCommands)

放入服务器plugins文件夹 重启服务器
命令可快速查找到你lore的对应格子 你只需要把物品放到对应位置

## 命令

* /loretimercommands find **lore** - 查找拥有该lore的物品在你背包什么格子

## 配置文件

```yml
无尽钻石:
  # 放在什么格子才生效 支持龙核
  slot: "40"
  # 扩展customDataMeta 按需开启 不需要注释掉即可
  # customDataMeta: 10026
  # 识别lore
  lore: '每10分钟获得一颗钻石'
  # 多少秒执行一次
  timer: 600
  # 原版物品奖励
  item:
    - 'diamond:1'
  # kether执行
  # 玩家变量: %player%
  kether:
    - "command 'say 成功执行' as console"
```

# 特点

> 龙核支持  
> 高扩展性,可以用它做出无限物品，获取每隔多久获得一次BUFF
> 可执行kether 直接物品奖励
> 可判断必须要放什么格子才能获取奖励
> 全异步线程 不卡服

# 价格

> 30元 无验证 购买联系QQ 3104026189

# 更新日志

* 2022.9.1 插件首次发布
* 2022.9.1 龙核支持