---
title: 限时物品(过期回收)
description: Minecraft 简单的限时物品插件
published: true
date: 2023-04-22T05:19:24.371Z
tags: 我的世界插件
editor: markdown
dateCreated: 2022-09-01T05:57:46.518Z
---

# 快速开始(TimeLimitedItems)
 
![](https://s1.ax1x.com/2022/09/01/v58QW4.png)  
放入服务器plugins文件夹 重启服务器

## 命令
> 物品库的LORE支持%player_name%变量

* /timelimiteditems save **id** - 保存手上的物品到物品库  
* /timelimiteditems give **player id time** - 将物品库的物品给玩家 并加上时间  
* /timelimiteditems final **player id 时间戳** - 将物品库物品给玩家 带上固定时间戳
<br>
* **time** 1d(一天) 1s(一秒) 1h(一小时)

## 配置文件

```yml
display:
  # 是否启用LORE显示时间
  enable: true
  # 时间显示格式
  format: "yyyy-MM-dd HH:mm:ss"
  # lore显示格式
  display: "&c到期时间: &f${format}"
# 检测的龙核槽位
dragonCore:
  - '龙核槽位1'
  - '龙核槽位2'
  - '龙核槽位3'
```

## MM兼容
![](https://s1.ax1x.com/2022/09/01/v58PJg.png)
> 您可以如图片所示 添加物品NBT 后面的数值为到期时间戳  
> 也可以实现限时物品
{.is-success}

## 其他插件兼容
> 只要能写物品NBT的插件就行了  
> nbt路径为 time-limited-items-time  
> 对应的值为到期时间戳
{.is-success}
 
# 特点
> 龙核兼容  
> 使用NBT判断物品到期时间  
> 无需玩家使用即可实现物品回收  
> 自带物品库  
> 全异步线程 不卡服  
{.is-success}

# 价格
> 50元 无验证 购买联系QQ 3104026189  
{.is-success}

# 更新日志
* 2022.9.1 插件首次发布
* 2022.9.1 龙核支持
* 2022.9.2 添加物品回收语言
* 2022.9.5 添加命令 final 添加对物品库玩家名变量支持