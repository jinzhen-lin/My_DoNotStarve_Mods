

本MOD由联机版Too Many Items（作者：Skull）修改而来，并跟随原MOD采用[GPL3协议](<https://www.gnu.org/licenses/gpl-3.0.html>)开源。

Too Many Items系列的MOD给有测试、演示需求的玩家提供了极大的便利，是一个伟大的MOD系列。但 [单机版本的Too Many Items](<https://steamcommunity.com/sharedfiles/filedetails/?id=579513934>) 和 [联机版本的Too Many Items](<https://steamcommunity.com/sharedfiles/filedetails/?id=551338671>) 相比少了很多有用的功能。为此，我将联机版本的Too Many Items 移植至单机版，重新实现了里面的若干功能并添加了若干在单机版饥荒可能会有用的新特性。

我的主要更改：

- 将UI界面移植至单机版（其实变化不大，主要是单机与联机兼容性）
- 删除了单机版不适用的功能、重新实现了部分功能、针对单机版添加了若干新特性
- 重新建立了单机版适用的完整物品列表与地图目标列表
- 补充了部分无法直接使用 SpawnPrefab 之类的命令直接生成的生物与建筑的生成方式。几个例子：
  - 桦树精：代码和桦树一样都是 deciduoustree ，直接生成的话只能得到桦树，需要另外处理
  - 秃鹫：生成倒是可以生成，但如果不做特殊处理，在它飞走的时候游戏会崩溃
  - 切斯特（暗影切斯特、冰雪切斯特）、鹈鹕（胖鹈鹕、火鹈鹕）、ROBIN
- 为生物、建筑列表的物品添加了图片。饥荒源码当中，除了可以放进背包栏以及科技栏里有的物品，其他物品基本没有提供图片，只有其动画。要图片的话需要专门从动画文件中提取。我添加的图片中有部分是下载自[饥荒Wiki](<https://dontstarve.fandom.com/wiki/Don%27t_Starve_Wiki>)  ，其他是我自己提取的。另外这也是本MOD的文件比联机版的原MOD大那么多的原因。

注意：

- 生物和建筑列表中的一些物品在本不属于它的世界当中生成时会直接崩溃，比如在哈姆雷特之外的世界生成蚁后会直接崩。我已经根据不同世界的情况移除了部分在该世界会导致崩溃的物品，但有可能有遗漏，而且更关键的是——我是在[最新的哈姆雷特测试版](<https://steamcommunity.com/games/219740/announcements/detail/1727601346322579127>)下做测试的，这个测试版主要特性是允许在哈姆雷特之外的世界建哈姆雷特的猪房，目前的正式版本通过代码在哈姆雷特之外生存这种猪人/猪房时会直接崩，考虑到这些特性未来也会添加进正式版就懒得另外弄了。
- 这个MOD目前的状态应该算是测试状态，有些东西没经过严格的测试（我自己一个人也没法做很多测试，有时候要考虑是否启动了DLC，以及处于哪个世界等等），可能会崩溃以及导致一些神奇的错误，出问题欢迎反馈，以及请不要在自己的正式存档使用，否则后果自负。
- 就算各种BUG已经基本移除，也强烈不建议在正式游玩中使用，会极大降低游戏乐趣
- 物品列表中，物品显示的名称下方是物品的代码，如果代码中有加号("+")，表示本MOD对其进行一定的特殊处理
- 不得不说单机版的中文支持相比于联机版真的差，这个MOD如果调为中文的话UI界面会挺混乱的，无力解决，建议英文版（我是指如果你习惯的话，最好整个游戏都不开中文MOD）。



未来计划：

- 解决各种崩溃问题
- 允许玩家将“其他”类别中的物品移入正式物品类别
- 提供其他MOD对本MOD中的物品类别、功能等进行调整的接口







# 主面板

生成物品的功能方面，包含了多个物品类别：

- 特殊（收藏）：收藏的物品
- 全部：包含了资源、武器、工具、衣物、礼物中的物品
- 食物、资源、武器、工具、衣物、礼物：生成后进入物品栏
- 生物、建筑：生成后出现在玩家附近
- 其他：以上类别没出现的物品（比如之后版本新加的）以及MOD物品会出现在这里，但包含了很多乱七八糟的物品，很容易崩溃

生成物品的方式：

- 单击生成 1 个物品。（可以在选项中更改）
- 右击生成 10 个物品。（可以在选项中更改）
- SHIFT + 单击或右击得到和物品生成数量份数的制作材料。
- CTRL + 点击加入或移除自定义物品列表（收藏）。

搜索时：

- Enter 键或点击任意位置：搜索输入的内容。
- UP 键：上个输入内容。
- DOWN 键：下个输入内容或清空输入的内容。
- ESC 键：退出输入。



此外还可以还有一些小功能，具体如下（括号中为相同按钮按住CTRL再点击的效果）：设置生命为满（为10%）、设置精神为满（为0）、设置饥饿为满（为0）、设置温度为25度（为环境温度）、设置湿度为0（为100）、设置伍迪的木头值为满（为0）、清空背包（清空背包+物品栏）、解毒（中毒）、游戏暂停/继续、上帝模式、创造模式、一击必杀模式



# 调试面板

- 季节：
  - 原版：夏季、冬季
  - 巨人国：春季、夏季、秋季、冬季
  - 船难：温季、风季、雨季、旱季
  - 哈姆雷特：温和季、湿润季、繁茂季、毁灭季
- 时间：下一段、1天后、5天后、10天后、20天后
- 速度：0.6倍速、正常速度、2倍速、3倍速
- 天气：闪电、开始/停止雨雪、开始/停止火山爆发（船难）、开始/停止飓风（船难）、开始/停止雾（哈姆雷特、湿润季）
- 玩家：解锁全部科技（不是创造模式）、解锁全部人物、更换角色并继续游戏、清空停尸房
- 实体：（范围内）删除、施肥、催熟、收获、拾取、冻结
- 驯化牛：战斗牛、骑行牛、宠物牛、普通牛
- 随从：添加、驱逐、健康、饥饿度、忠诚度
- 游戏：回档、存档、进入下一个世界、重置世界ID为1（正常来说进入下一个世界后ID会加1）、前往生成模式世界、前往船难世界、前往哈姆雷特世界
- 传送：记录当前所处位置、传送到已记录的位置
- 地图：全图（暂时，重新加载游戏后丢失）、全图（永久）、清空地图、在地图上显示当前遗迹内全部房间（HAMLET）、传送到某些指定地点（不同世界内列表不同）。传送到指定地点这一项专门针对做了一些优化：
  - 如果玩家在陆地上但目标在水面上，则会生成木筏并乘坐上再传送（不然直接淹死了）
  - 如果玩家在水面上但目标在陆地上，则会把船停在原地再传送（不然船会直接毁坏）
  - 在哈姆雷特中，避免了直接跨房间传送时会被卡主的问题
