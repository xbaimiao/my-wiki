# 特色
> 支持收购/出售 ItemsAdders 的物品
> 限制(全服/玩家) 当日出售或收购数量
> 支持 MYSQL,SQLITE 储存限购数据 (这意味着可以全服同步)
> 一键出售/购买
> 多页商店
{.is-success}

# 快速开始

## 安装
> 下载插件JAR 放入服务器Plugins文件夹后重启服务器
{.is-info}

## 配置文件
```yml
# 请勿修改此项
date: 0
# 启用mysql
mysql:
	# 是否启用MYSQL储存限购数据
  enable: false
  host: localhost
  port: 3306
  user: "root"
  password: "123456"
  database: "shoppro"
```

## 命令
> /shoppro reload -> 重载插件
> /shoppro resetLimit -> 手动重置限购数据
> /shoppro open **商店名** -> 打开一个商店
> /shoppro open **商店名** **玩家** -> 为玩家打开一个商店
> /shoppro sellAll **商店名** -> 根据此商店一键出售背包所有物品
> /shoppro sellAll **商店名** **玩家** -> 根据此商店一键出售背包所有物品
![shoppro-sellall.png](/shoppro/shoppro-sellall.png)
{.is-success}


## 命令权限
> /shoppro reload -> `shoppro.reload`
> /shoppro resetLimit -> `shoppro.resetlimit`
> /shoppro open **商店名** -> `shoppro.command.open.商店名`
> /shoppro open **商店名** **玩家** -> `shoppro.command.open.admin`
> /shoppro sellAll **商店名** -> `shoppro.command.sellall`
> /shoppro sellAll **商店名** **玩家**  `shoppro.command.sellall.admin`

# 创建商品

## 创建普通商品

```yml
    material: IRON_INGOT
    name: '&f&l铁锭'
    price: 10
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
```

## 创建限购/限售物品
```yml
    material: STONE
    name: '石头'
    # 每日总限制
    limit: 5000
    # 每个玩家限制
    limit-player: 500
    # 物品金额
    price: 2
    lore:
      - '&e| &7这里可以购买&6 ${name}'
      - '&e| &7购买单价 &6${price}'
      - '&e| &7你的余额 &6${money}'
      - ''
      - '&e|&6 左击 &7购买 &6单个'
      - '&e|&6 右击 &7购买 &6一组 &7需要 &6${price64}'
      - ''
      - '&e| &7限买公示:'
      - '&e| &7每人限制购买: ${limit}'
      - '&e| &7全服限制购买: ${allLimit}'
      - '&e| &7您已购买: ${limit-player}'
      - '&e| &7全服剩余: ${limit-server}'
```


## 创建ItemsAdder物品
```yml
		# IA开头 :分割 中间为Material 后面为CustomData
    material: 'IA:PAPER:10007'
    name: 'itemsadder'
    price: 20
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
```

## 创建一个头颅装饰的收购物品
```yml
		# HEAD开头
    material: 'HEAD:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYWU4ZTY3MGE3OWI2MTYzMzRiYzFmYjkxMzkxMzJmYjM1YzU3ZGRhNjk3NWFmOWNlNDgzMzNlOTRhYTZjOTU3MyJ9fX0='
    name: '煤炭收购'
    # 由于material由头颅装饰了 实际收购的物品写到这里
    item: COAL
    price: 1
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
```

## 创建一个头颅装饰的出售物品

```yml
		# HEAD开头
    material: 'HEAD:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYWU4ZTY3MGE3OWI2MTYzMzRiYzFmYjkxMzkxMzJmYjM1YzU3ZGRhNjk3NWFmOWNlNDgzMzNlOTRhYTZjOTU3MyJ9fX0='
    name: '煤炭购买'
    price: 2
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
    # 关闭物品给予 执行命令发货 
    vanilla: false
    commands:
      - '[console] give %player% COAL 1'
```

## 创建一个非商品,点击执行命令的按钮
```yml
    material: ARROW
    name: '&f下一页'
    lore:
      - '&f点击前往下一页'
    is-commodity: false
    commands:
      - '[open] 默认收购商店'
```
> 更多命令执行方式请查看命令动作

# 命令动作
## 可用命令动作
> 
> [tell] 给玩家发送一条消息
> [console] 控制台执行一条命令
> [player] 点击/购买此物品的玩家执行一条命令
> [op] 点击/购买此物品的玩家以OP权限执行一条命令
> [open] **菜单名** 打开另一个菜单
> [close] 关闭商店
{.is-success}


## 示例配置文件

```yml
type: sell
name: "自带收购商店"
title: "系统收购商店"

slots:
  - 'NNNNNNNNN'
  - 'NQWERTYUN'
  - 'NIOP    N'
  - 'NNNNNNNNX'

items:
  N:
    material: GLASS_PANE
    name: ' '
    lore:
      - ' '
    is-commodity: false
  X:
    material: ARROW
    name: '&f下一页'
    lore:
      - '&f点击前往下一页'
    is-commodity: false
    commands:
      - '[open] 默认收购商店'
  Q:
    material: COAL
    name: '&f&l煤炭'
    price: 0.5
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
    # 关闭此选项 可只执行命令 不给原版物品
    vanilla: false
    commands:
      - '[console] give %player% COAL'
```

## 实现商店跳转

```yml
X:
    material: ARROW
    name: '&f下一页'
    lore:
      - '&f点击前往下一页'
    is-commodity: false
    commands:
      - '[open] 默认收购商店'
```

# 自定义货币

## 介绍
> 本插件已预设了 Vault 和 Points支持
> 但是考虑但服主们可能会有其他货币的需求 故开发了自定义

## 使用教程
> 自定义货币文件放在 /plugins/ShopPro/currencys 文件夹里
> 以下是插件自带的一个文件

```yml
# 货币的识别名 可在物品哪里指定为你自定义的货币
# 例子
# A:
#  material: STONE
#  currency: DIY1
name: "DIY1"
takeCommand: "扣除货币的指令 %player% 为玩家变量 %num% 为数量"
giveCommand: "给货币的指令 %player% 为玩家变量 %num% 为数量"
amountPapi: "你自定义的这个货币的papi变量"
```

## 为你的商品使用自定义货币
* 只需要如下填写 currency 即可
* 不填默认为 vault
```yml
    material: STONE
    # 指定货币 如果不指定默认Vault
    # 已预设点券支持 为: "points"
    # 您可在 currencys 里自定义货币
    currency: points
    name: '石头'
    # 每日限购买
    limit: 5000
    # 每个玩家限购买
    limit-player: 500
    # 物品金额
    price: 2
```

# 购买
> 插件无验证 无IP与端口限制
> 价格 98RMB
> 购买联系QQ 3104026189
{.is-info}

# 功能介绍

> [Limit_限制购买与出售](/ShopPro/Limit) 点击左侧查看详情
> [Shops_自带的商店介绍](/ShopPro/Shops) 点击左侧查看详情
{.is-success}