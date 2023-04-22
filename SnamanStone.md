---
title: 类贤者之石插件
description: 
published: true
date: 2023-04-22T05:19:42.292Z
tags: 我的世界插件
editor: markdown
dateCreated: 2022-09-02T01:36:40.593Z
---

# 快速开始
> 将插件放入plugins文件夹 重启服务器即可

## 配置文件
> config.yml
```yml
setting:
  # 禁用的世界
  worlds:
    - 'lobby'
item:
  material: 'head:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvN2JhM2JlODNlZDQ3NTAyZmIxYTE0MWQzYTc4NWZmOTZmMjg1NmVmMzg2MjIzMzg1NDQwNWRiZjhkYWJlNDI3In19fQ=='
  #可以支持头颅材质
  name: '&{#FFFFFF}贤&{#FF0000}者&{#D8BFD8}之&{#9932CC}石'
  #如果可以的能不能支持一下RGB 格式 '&{#FFFFF}贤者之石'
  #包括下面的lore
  lore:
    - '&f右键      Shift+右键'
    - '&f石头 => 圆石      石头 => 草方块'
    - '&f圆石 => 石头      圆石 => 草方块'
    - '&f草方块 => 沙子      草方块 => 圆石'
    - '&f泥土 => 沙子      沙子 => 圆石'
    - '&f沙子 => 草方块      流动岩浆 => 黑曜石'
    - '&f沙子 => 泥土'
    - '&f黑曜石 => 流动岩浆'
    - '&f冰块 => 流动水'
    - '&f砂砾 => 沙石'
    - '&f沙石 => 砂砾'
    - '&f原版7种树苗顺序转化	原版7种树苗倒序转化'
    - '&f原版7种原木顺序转化	原版7种原木倒序转化'
    - '&f原版7种树叶顺序转化	原版7种树叶倒序转化'
    - '&f原版16种羊毛顺序转化	原版16种羊毛倒序转化'
    - '  '
  enchant: []
  flags:
    - 'HIDE_ENCHANTS'
    - 'HIDE_DESTROYS'
    - 'HIDE_POTION_EFFECTS'
  #以上 enchant flags 词条可以按照自己的需求写或者不写都行那种不是强制性的
  itembind: false
  #是否开启物品绑定？
  bddefault: '物品主人: [持有立即绑定]'
  #如果itembind: true 这句lore加在上面lore:这个词条最后一句之后
  bdafter: '物品主人: [%player_name%]'
  #玩家持有过后 “bddefault: '物品主人: [持有立即绑定]'” 自动绑定自己的ID，这个物品的任何功能仅限于物品主人使用
abilities:
  right:
    - 'stone-cobblestone'
    #石头 => 圆石
    - 'cobblestone-stone'
    #圆石 => 石头
    - 'grass_block-sand'
    #草方块 => 沙子
    - 'dirt-sand'
    #泥土 => 沙子
    - 'sand-grass_block'
    #沙子 => 草方块
    - 'sand-dirt'
    #沙子 => 泥土
    - 'obsidian-lava'
    #黑曜石 => 流动岩浆
    - 'gravel-sandstone'
    #砂砾 => 沙石
    - 'sandstone-gravel'
    #沙石 => 砂砾
    - 'saplingtoggle'
    #原版7种树苗顺序转化
    - 'logtoggle'
    #原版7种原木顺序转化
    - 'leavestoggle'
    #原版7种树叶顺序转化
    - 'wooltoggle'
    #原版16种羊毛顺序转化
  shift_right:
    - 'stone-grass_block'
    #石头 => 草方块
    - 'cobblestone-stone'
    #圆石 => 草方块
    - 'grass_block-cobblestone'
    #草方块 => 圆石
    - 'sand-cobblestone'
    #沙子 => 圆石
    - 'saplingtoggle'
    #原版7种树苗顺序转化
    - 'logtoggle'
    #原版7种原木顺序转化
    - 'leavestoggle'
    #原版7种树叶顺序转化
    - 'wooltoggle'
    #原版16种羊毛顺序转化
```
> zh_CN.yml
```yml
reload: "&7[&a贤者之石&7] 重载完成"
nochange: "&7[&a贤者之石&7] 该物品不可变换,请尝试 &a右击 &7或 &a潜行+右击"
giveitem: "&7[&a贤者之石&7] 物品已放入你的背包"
giveitem-player: "&7[&a贤者之石&7] 物品已放入{0}的背包"
world-ban: "&7[&a贤者之石&7] 已在此世界禁用贤者之石"
world-res: "&7[&a贤者之石&7] 你不能在别人的领地使用贤者之石"
```

## 命令
> /snamanstone reload 重载插件  
> /snamanstone item 获得贤者之石  
> /snamanstone item **player** 将贤者之石给这个玩家  

# 图片介绍
![贤者之石介绍.gif](/贤者之石介绍.gif)