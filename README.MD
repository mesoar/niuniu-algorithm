# 牛仔游戏（开心牛仔）算法

## 规则

> 牌型有如下几种，牌型大小: 五小牛 > 炸弹 > 五花牛 > 四花牛 > 牛牛 > 有牛 > 无牛

|牌型|说明|
|:---:|:----|
|五小牛|五张牌的点数加起来小于10，且每张牌点数都小于5，例如a、3、2、a、2。|
|炸弹|五张牌中有4张牌点数相同的牌型，例如：2、2、2、2、k。|
|五花牛|五张牌全由j～k组成，例如j、j、q、q、k。|
|四花牛|五张牌全由10～k组成且只有一张10，例如10、j、j、q、k。|
|牛牛|五张牌中第一组三张牌和第一组二张牌之和分别为10的整数倍。 3、7、k、10、j。|
|有牛|五张牌中有三张的点数之和为10点的整数倍，并且另外两张牌之和与10进行取余，所得之数即为牛几。例如: 2、8、j、6、3，即为牛9。牛一到牛6为1倍，牛七到牛九位2倍！|
|无牛|五张牌中没有任意三张牌点数之和为10的整数倍。例如: a、8、4、k、7。|

> 当牌型相同的情况下，按照一下标准分大小：

依次比较单牌大小，单牌大的获胜；所有单牌相同的情况下，比较最大那张牌的花色，花色大的牌大；
(花色大小依次：黑桃 > 红桃 > 梅花 > 方块)


## 使用

```php
<?php
//创建实例
$niu = new NiuNiu();
//随机生成3位玩家， 2种方式二选一，但是如果手工填入的话，需要自己管理随机性和牌的唯一性
$niu->generate(3);
//手工填入2位玩家
//$niu->setPlayerCard('player_1', [[1, 4, 1], [2, 4, 2], [3, 4, 3], [4, 4, 4], [5, 2, 5]]);
//$niu->setPlayerCard('player_2', [[1, 3, 1], [2, 3, 2], [3, 3, 3], [4, 3, 4], [5, 3, 5]]);
//执行计算
$result = $niu->execute();
$players = $niu->getPlayersCards();
$time2 = microtime(true);
//输出剩余的牌
//var_dump($niu->getLeftCards());
//输出玩家牌
var_dump($players);
//输出结果
echo '<pre>';
print_r($result);
```

## 问题

欢迎 issues 哦。
