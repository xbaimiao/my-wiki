# sell.yml

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
  W:
    material: IRON_INGOT
    name: '&f&l铁锭'
    price: 10
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  E:
    material: GOLD_INGOT
    name: '&f&l金锭'
    price: 13
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  R:
    material: COPPER_INGOT
    name: '&f&l铜锭'
    price: 12
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  T:
    material: DIAMOND
    name: '&f&l钻石'
    price: 20
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  Y:
    material: BREAD
    name: '&f&l面包'
    price: 3
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  U:
    material: CAKE
    name: '&f&l蛋糕'
    price: 30
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  I:
    material: PUMPKIN_PIE
    name: '&f&l南瓜派'
    price: 4
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'
  O:
    material: MUSHROOM_STEW
    name: '&f&l蘑菇煲'
    price: 2
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'


  # itemsadder 物品
  P:
    material: 'IA:PAPER:10007'
    name: ' '
    price: 20
    lore:
      - '&a&l左键 &f&l出售单个'
      - '&a&l右键 &f&l出售一组'
      - '&a&lShift + 右键 &f&l出售背包所有可出售物品'
      - ''
      - '&a&l收购价格 &c&l${price}'

```

# limit-buy.yml

```yml
# 商店类型
# buy 为出售商店
# sell 为收购商店
type: sell
name: "默认收购商店"
title: "系统收购商店"
# 物品摆放顺序
slots:
  - 'NNNNNNNNN'
  - 'NAB     N'
  - 'NNNNNNNNN'
items:
  N:
    material: GLASS_PANE
    name: ' '
    lore:
      - ' '
    # 是否为商品
    is-commodity: false
  # 普通物品收购示例
  A:
    material: STONE
    name: '石头'
    # 每日限出售
    limit: 5000
    # 每个玩家限出售
    limit-player: 500
    # 物品金额
    price: 1
    lore:
      - '&e| &7这里可以出售你背包里面的&6 ${name}'
      - '&e| &7收购单价 &6${price}'
      - '&e| &7你的余额 &6${money}'
      - ''
      - '&e|&6 左击 &7出售 &6单个'
      - '&e|&6 右击 &7出售 &6一组 &7获得 &6${price64}'
      - '&e|&6 Shift + 右击 &7出售 &6背包所有 &7获得${priceAll}'
      - ''
      - '&e| &7限售公示:'
      - '&e| &7每人限制出售: ${limit}'
      - '&e| &7全服限制出售: ${allLimit}'
      - '&e| &7您已出售: ${limit-player}'
      - '&e| &7全服剩余: ${limit-server}'
  # itemsadder 物品收购示例
  # 需要使用IA:前缀 中间为物品材质 后面为物品customData,如果是药水需要在添加一个 CustomPotionColor
  B:
    material: 'IA:PAPER:10001'
    name: 'IA物品名'
    # 每日限出售
    limit: 5000
    # 每个玩家限出售
    limit-player: 500
    # 物品金额
    price: 1
    lore:
      - '&e| &7这里可以出售你背包里面的&6 ${name}'
      - '&e| &7收购单价 &6${price}'
      - '&e| &7你的余额 &6${money}'
      - ''
      - '&e|&6 左击 &7出售 &6单个'
      - '&e|&6 右击 &7出售 &6一组 &7获得 &6${price64}'
      - '&e|&6 Shift + 右击 &7出售 &6背包所有 &7获得${priceAll}'
      - ''
      - '&e| &7限售公示:'
      - '&e| &7每人限制出售: ${limit}'
      - '&e| &7全服限制出售: ${allLimit}'
      - '&e| &7您已出售: ${limit-player}'
      - '&e| &7全服剩余: ${limit-server}'

```

# limit-sell.yml

```yml
# 商店类型
# buy 为出售商店
# sell 为收购商店
type: sell
name: "默认收购商店"
title: "系统收购商店"
# 物品摆放顺序
slots:
  - 'NNNNNNNNN'
  - 'NAB     N'
  - 'NNNNNNNNN'
items:
  N:
    material: GLASS_PANE
    name: ' '
    lore:
      - ' '
    # 是否为商品
    is-commodity: false
  # 普通物品收购示例
  A:
    material: STONE
    name: '石头'
    # 每日限出售
    limit: 5000
    # 每个玩家限出售
    limit-player: 500
    # 物品金额
    price: 1
    lore:
      - '&e| &7这里可以出售你背包里面的&6 ${name}'
      - '&e| &7收购单价 &6${price}'
      - '&e| &7你的余额 &6${money}'
      - ''
      - '&e|&6 左击 &7出售 &6单个'
      - '&e|&6 右击 &7出售 &6一组 &7获得 &6${price64}'
      - '&e|&6 Shift + 右击 &7出售 &6背包所有 &7获得${priceAll}'
      - ''
      - '&e| &7限售公示:'
      - '&e| &7每人限制出售: ${limit}'
      - '&e| &7全服限制出售: ${allLimit}'
      - '&e| &7您已出售: ${limit-player}'
      - '&e| &7全服剩余: ${limit-server}'
  # itemsadder 物品收购示例
  # 需要使用IA:前缀 中间为物品材质 后面为物品customData,如果是药水需要在添加一个 CustomPotionColor
  B:
    material: 'IA:PAPER:10001'
    name: 'IA物品名'
    # 每日限出售
    limit: 5000
    # 每个玩家限出售
    limit-player: 500
    # 物品金额
    price: 1
    lore:
      - '&e| &7这里可以出售你背包里面的&6 ${name}'
      - '&e| &7收购单价 &6${price}'
      - '&e| &7你的余额 &6${money}'
      - ''
      - '&e|&6 左击 &7出售 &6单个'
      - '&e|&6 右击 &7出售 &6一组 &7获得 &6${price64}'
      - '&e|&6 Shift + 右击 &7出售 &6背包所有 &7获得${priceAll}'
      - ''
      - '&e| &7限售公示:'
      - '&e| &7每人限制出售: ${limit}'
      - '&e| &7全服限制出售: ${allLimit}'
      - '&e| &7您已出售: ${limit-player}'
      - '&e| &7全服剩余: ${limit-server}'
```