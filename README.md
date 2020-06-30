# GS新周目插件进度

## 插件列表

这里列的是将要选用的插件。

| 插件名称                                                     | 功能                             | 适配情况     |
| ------------------------------------------------------------ | -------------------------------- | ------------ |
| CGBackup                                                     | 自动备份、自动停服               | 有待继续开发 |
| [Plugman](https://dev.bukkit.org/projects/plugman)           | 插件管理                         | 兼容         |
| [Vault](https://www.spigotmc.org/resources/vault.34315/)     | 权限、经济、聊天API              | 兼容         |
| [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) | 插件共享变量                     | 兼容         |
| [ChatEx](https://www.spigotmc.org/resources/chatex.71041/)   | 聊天管理，屏蔽敏感词、广告，前缀 | 兼容         |
| [LuckPerms](https://luckperms.net/)                          | 权限管理，前缀                   | 兼容         |

## 插件调研

### AutoSaveWorld

#### 功能

* 自动保存
* 自动备份
* 存档上传
* 插件管理
* 自动清理

#### 问题

* 三年没有更新
* 备份有BUG

#### 解决方法

改用CGBackup和Plugman。

### CGBackup

#### 功能

* 自动保存
* 自动备份
* 存档上传

#### 问题

1. 自动保存功能应该删掉
2. 需要添加控制存档数量的功能
3. 自动备份改为指定的时间点
4. 存档上传功能应该删掉

#### 解决方法

继续开发

### Plugman

#### 功能

插件管理

### ChatEx

#### 功能

* 聊天格式
* 玩家加入、退出服务器的信息
* 头衔
* 敏感词过滤
* 广告屏蔽

## 功能需求

### 头衔

#### 要求

信息前面加上前缀：`[prefix]id: content`，Tablist里面也要有，另外prefix需要颜色。

#### 实现

头衔的实现：底层依赖Vault提供API，头衔由LuckPerms设置，由ChatEx显示。

#### 效果

比如我的头衔是红色的`FOX`。首先是聊天：

![头衔聊天展示](./images/prefix_message.png)

其次是Tablist中的效果：

![头衔Tablist展示](./images/prefix_tablist.png)

#### 设置方法

通过LuckPerms的子命令`meta`修改。

两个参考资料：[LuckPerms Wiki](https://luckperms.net/wiki/Meta-Commands) 和 [颜色代码](https://minecraft.gamepedia.com/Formatting_codes)

```
lp user _zhao_ meta addprefix 90 [&cFOX&f]
```

这样就添加了红色的`FOX`头衔，优先级为90。需要取消头衔的时候：

```
lp user _zhao_ meta removeprefix 90
```

### 剩下没弄的

牌子锁

性能优化

彩蛋：烧石头有几率获得矿石原矿

定时备份：早八点晚八点，本地

提前5分钟、1分钟、30秒提醒关服

早上八点停服更新paper

AFK挂机，挂机有奖励

@功能

公告

主群和服务器聊天双向同步

箱子商店，银行系统

不要EssentialsX

小黑屋

前缀：颜色



