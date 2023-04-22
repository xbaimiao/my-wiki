---
title: 限购/限售(Limit)
description: 限制玩家与全服出售
published: true
date: 2022-09-09T15:34:24.351Z
tags: 
editor: markdown
dateCreated: 2022-09-08T15:11:52.227Z
---

# 图片介绍
![gif_2022-9-9_23-33-16.gif](/gif_2022-9-9_23-33-16.gif)

# 你只需要如以下所示范写上限购数量即可

```yml
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
```